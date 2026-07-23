# Prompt Template: [Task Name]

**Date:** 2026-07-22
**Author:** Igor Kartun — Engineering
**Project:** Meridian Retail Group (MRG)
**Model:** Claude sonnet 4.6
**DIAL location:** [DIAL shared link or folder path]
**Committed location:** https://github.com/ikartun/AI-Factory.git

---

## Purpose

Code review: technical and for acceptance criteria of the corresponding story.
It's for code reviewers (developers) at code review SDLC stage.

---

## Variable Placeholders

| Placeholder           | Description                 | Example value                                                                                                                                                                                                                                                            |
|-----------------------|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `{{user_story_desc}}` | The story with description  | Merge customers loyalty accounts across regions                                                                                                                                                                                                                          |
| `{{user_story_ac}}`   | Acceptance criteria         | For each customer find all fragmented loyalty accounts across regions using email and name;<br/>Merge all accounts into one per customer combining all information from those accounts into the merged account;<br/>Update customer_accounts and customer_orders tables. |
| `{{pr_diff}}`         | A text with diff for the PR | diff --git a/data/merge_customer_accounts.sql b/data/merge_customer_accounts.sql new file mode 100644                                                                                                                                                                    |

---

## Output Format Instruction

A table with the list of technical issues and a table wit pass/fail per AC item with possible explanation why it failed.
Tables columns. Technical table: File, Issue, Severity. AC table: AC item, Pass/Fail, Explanation. 

---

## Prompt Body

You are a code reviewer. Check the PR diff using {{pr_diff}} and review it in terms of technical code review. Then according to {{user_story_ac}} and {{user_story_desc}} - review the PR to check if ACs pass/fail.
Provide the result in output format: a table with the list of technical issues (File, Issue, Severity columns) and a table wit pass/fail per AC item with possible explanation why it failed (AC item, Pass/Fail, Explanation columns).

---

## Test Run (Author)

**Input values used:**
- `{{user_story_desc}}` = Merge customers loyalty accounts across regions
- `{{user_story_ac}}` = For each customer find all fragmented loyalty accounts across regions using email and name;<br/>Merge all accounts into one per customer combining all information from those accounts into the merged account;<br/>Update customer_accounts and customer_orders tables.
- `{{pr_diff}}` = diff --git a/data/merge_customer_accounts.sql b/data/merge_customer_accounts.sql
new file mode 100644
index 0000000..887203e --- /dev/null
+++ b/data/merge_customer_accounts.sql
@@ -0,0 +1,82 @@
+-- User Story:
+-- Merge customer loyalty accounts across regions.
+--
+-- Matching criteria:
+-- Customers are considered the same when they have the same:
+--   1. Email
+--   2. First name
+--   3. Last name
+BEGIN TRANSACTION;

+-- Step 1: Find customers with fragmented loyalty accounts
+WITH duplicated_customers AS (
SELECT
       LOWER(email)      AS normalized_email,
        LOWER(first_name) AS normalized_first_name,
        LOWER(last_name)  AS normalized_last_name,
        MIN(customer_account_id) AS primary_account_id
    FROM customer_accounts
    GROUP BY
        LOWER(email),
        LOWER(first_name),
        LOWER(last_name)
    HAVING COUNT(*) > 1
),


+-- Step 2: Map every fragmented account to one primary account
account_mapping AS (
    SELECT
        ca.customer_account_id AS old_account_id,
        dc.primary_account_id  AS merged_account_id
    FROM customer_accounts ca
    JOIN duplicated_customers dc
        ON LOWER(ca.email) = dc.normalized_email
       AND LOWER(ca.first_name) = dc.normalized_first_name
       AND LOWER(ca.last_name) = dc.normalized_last_name
)


+-- Step 3: Update customer_orders to reference the merged account
+UPDATE customer_orders orders
+SET customer_account_id = mapping.merged_account_id
+FROM account_mapping mapping
+WHERE orders.customer_account_id = mapping.old_account_id
AND mapping.old_account_id <> mapping.merged_account_id;


+-- Step 4: Combine loyalty information from all fragmented accounts
+UPDATE customer_accounts primary_account
+SET
    loyalty_points = merged_data.total_loyalty_points,
    lifetime_spend = merged_data.total_lifetime_spend,
    last_order_date = merged_data.latest_order_date,
    updated_at = CURRENT_TIMESTAMP
FROM (
    SELECT
        mapping.merged_account_id,
        SUM(COALESCE(account.loyalty_points, 0)) AS total_loyalty_points,
        SUM(COALESCE(account.lifetime_spend, 0)) AS total_lifetime_spend,
        MAX(account.last_order_date) AS latest_order_date
    FROM account_mapping mapping
    JOIN customer_accounts account
        ON account.customer_account_id = mapping.old_account_id
    GROUP BY mapping.merged_account_id
+) merged_data
+WHERE primary_account.customer_account_id =
      merged_data.merged_account_id;

+-- Step 5: Delete fragmented customer accounts
DELETE FROM customer_accounts
WHERE customer_account_id IN (
    SELECT old_account_id
    FROM account_mapping
    WHERE old_account_id <> merged_account_id
);


+COMMIT;
\ No newline at end of file

**Output quality:** It was usable with needed explanation what was not correct

---

## Peer Review

**Reviewer:** Igor Kartun — Engineering
**Date reviewed:** 2026-07-23
**Model used by reviewer:** Claude sonnet 4.6

**Reviewer input values used:**
- `{{user_story_desc}}` = remove duplicate customer loyalty accounts across regions
- `{{user_story_ac}}` = For each customer find all duplicate loyalty accounts accross regions using emai and name. Keep only the most recently created account. Delete all related customer orders and customer transactions associated with the removed accounts. Delete the duplicate customer accounts.
- `{{pr_diff}}` = diff --git a/data/delete_dupl_cust_accts.sql b/data/delete_dupl_cust_accts.sql
new file mode 100644
index 0000000..94d3037
--- /dev/null
+++ b/data/delete_dupl_cust_accts.sql
@@ -0,0 +1,85 @@
+-- User Story:
+-- Remove duplicate customer loyalty accounts across regions.
+--
+-- Duplicate matching criteria:
+--   1. Email
+--   2. First name
+--   3. Last name
+--
+-- For each customer, retain the most recently created account
+-- and delete all older accounts and their related data.


+BEGIN TRANSACTION;


+-- Step 1: Rank customer accounts within each duplicate group.
+-- The newest account receives rank 1 and will be retained.

+CREATE TEMPORARY TABLE duplicate_accounts AS
+SELECT
customer_account_id,
ROW_NUMBER() OVER (
       PARTITION BY
           LOWER(TRIM(email)),
           LOWER(TRIM(first_name)),
           LOWER(TRIM(last_name))
       ORDER BY
           created_at DESC,
           customer_account_id DESC
) AS account_rank
+FROM customer_accounts;


+-- Step 2: Store the IDs of the older duplicate accounts
+-- that must be deleted.

+CREATE TEMPORARY TABLE accounts_to_delete AS
+SELECT
customer_account_id
+FROM duplicate_accounts
+WHERE account_rank > 1;


+-- Step 3: Store orders associated with the accounts
+-- that will be deleted.

+CREATE TEMPORARY TABLE orders_to_delete AS
+SELECT
customer_order_id
+FROM customer_orders
+WHERE customer_account_id IN (
SELECT customer_account_id
FROM accounts_to_delete
+);


+-- Step 4: Delete transactions associated with those orders.
+-- Transactions must be deleted first because they reference orders.

+DELETE FROM customer_transactions
+WHERE customer_order_id IN (
SELECT customer_order_id
FROM orders_to_delete
+);


+-- Step 5: Delete orders associated with the older accounts.

+DELETE FROM customer_orders
+WHERE customer_order_id IN (
SELECT customer_order_id
FROM orders_to_delete
+);


+-- Step 6: Delete the older duplicate customer accounts.

+DELETE FROM customer_accounts
+WHERE customer_account_id IN (
SELECT customer_account_id
FROM accounts_to_delete
+);


+COMMIT;
\ No newline at end of file

| Review question | Reviewer answer                     |
|---|-------------------------------------|
| Could you run the template without asking the author anything? | Yes / No — Yes, it's fully detailed |
| Was the output format what you expected? | Yes / No — Yes, exactly             |
| Would you use this template on your own work? | Yes / No — Yes, why not             |
| One concrete improvement suggestion | Nothing                             |

---

## Revision History

| Version | Date       | Change | Author      |
|---|------------|---|-------------|
| 1.0 | 2026-07-23 | Added module 020 kata 2 | Igor Kartun |