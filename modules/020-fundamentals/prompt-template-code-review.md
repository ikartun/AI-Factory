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

| Placeholder           | Description                                     | Example value                                                                                                                                                                                                                                                            |
|-----------------------|-------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `{{user_story_desc}}` | The story with description                      | Merge customers loyalty accounts across regions                                                                                                                                                                                                                          |
| `{{user_story_ac}}`   | Acceptance criteria | For each customer find all fragmented loyalty accounts across regions using email and name;<br/>Merge all accounts into one per customer combining all information from those accounts into the merged account;<br/>Update customer_accounts and customer_orders tables. |
| `{{pr_url}}`          | The link for PR in code repo                  | [Realistic example]                                                                                                                                                                                                                                                      |

---

## Output Format Instruction

[Tell the model exactly what format to return. Be specific: e.g., "Return a markdown table with columns X, Y, Z. Maximum 10 rows. No preamble."]

---

## Prompt Body

[Full prompt text. Use {{placeholder}} syntax for all variable inputs. The prompt must be runnable by a teammate with zero explanation from you.]

---

## Test Run (Author)

**Input values used:**
- `{{placeholder_1}}` = [value you used]
- `{{placeholder_2}}` = [value you used]

**Output quality:** [One sentence — was the output usable as-is, or did you revise?]

---

## Peer Review

**Reviewer:** [Name — Role]
**Date reviewed:** YYYY-MM-DD
**Model used by reviewer:** [Model name]

**Reviewer input values used:**
- `{{placeholder_1}}` = [value reviewer used]
- `{{placeholder_2}}` = [value reviewer used]

| Review question | Reviewer answer |
|---|---|
| Could you run the template without asking the author anything? | Yes / No — [one sentence] |
| Was the output format what you expected? | Yes / No — [one sentence] |
| Would you use this template on your own work? | Yes / No — [one sentence] |
| One concrete improvement suggestion | [One sentence] |

---

## Revision History

| Version | Date | Change | Author |
|---|---|---|---|
| 1.0 | YYYY-MM-DD | Initial commit | [Name] |
| 1.1 | YYYY-MM-DD | Post-review update | [Name] |