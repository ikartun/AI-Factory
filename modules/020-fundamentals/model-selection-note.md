# Model Selection Note

**Date:** 2026-07-16
**Author:** Igor Kartun — Engineering
**Project:** Meridian Retail Group (MRG)
**Task:** Generate unit tests for a new method
**Committed location:** [Repo path or shared folder URL]

---

## Evaluation Criteria

| # | Criterion | Why it matters for this task                                                                          |
|---|-----------|-------------------------------------------------------------------------------------------------------|
| 1 | line coverage | to quickly find if any changed line of code breaks application                                        |
| 2 | edge-case coverage | to catch all possible input parameters that can affect method behaviour                               |
| 3 | no hardcoded test data | if test data is a dataset - it should be in a data file not in the code to make the code clear enough |
| 4 | same test framework as existing tests | to unify tests approach                                                                               |

---

## Prompt Used

I need to write unit test for create_features method. spline_deriv_set method should be mocked. Use pytest framework. The test should be a full line coverage, cover edge cases, no hardcoded literals — pull any test data into a resources file instead.

---

## Output Comparison

### Model A:  Gemini 3.5 flash
> RESOURCE_PATH = os.path.join(os.path.dirname(__file__), "test_resources.json")

> def load_test_resources():
    with open(RESOURCE_PATH, "r") as f:
        return json.load(f)

> TEST_DATA = load_test_resources()

> @pytest.mark.parametrize("case_name", list(TEST_DATA.keys()))
def test_create_features(case_name):
    """
    Unit test targeting 'create_features' to achieve 100% code coverage.
    All parameters, mock responses, and expected behaviors are pulled from test_resources.json.
    """
    case_config = TEST_DATA[case_name]

    # 1. Parse and build input DataFrames from the config
    interp_df = pd.DataFrame(case_config["input_df_data"])
    facility_id = case_config["facility_id"]

    # 2. Dynamic, version-agnostic mock function for spline_deriv_set
    def mock_spline_deriv_set(sheet):
        # A. Check columns (for older pandas versions)
        if "cycle_id_open" in sheet.columns:
            cycle_id = str(sheet["cycle_id_open"].iloc[0])

### Model B: Claude sonnet 4.6
> _MOCK_TARGET = "main.spline_deriv_set"

> def _make_df(data: dict) -> pd.DataFrame:
    """Build a DataFrame from a test-data dict, parsing TimeOfSample to datetime."""
    df = pd.DataFrame(data)
    df[COL_TIME] = pd.to_datetime(df[COL_TIME])
    return df


> def _zero_side_effect(group_df: pd.DataFrame) -> np.ndarray:
    """Mock side-effect: returns a zero array whose length matches the input group."""
    return np.zeros(len(group_df))


> @pytest.fixture
def mock_spline():
    with patch(_MOCK_TARGET, side_effect=_zero_side_effect) as m:
        yield m


> class TestEarlyReturn:
    """open_pressures has 0 or 1 rows → return empty DataFrame immediately."""

    def test_no_open_rows_returns_empty_dataframe(self):
        result = create_features(_make_df(NO_OPEN_ROWS), FACILITY_ID)
        assert isinstance(result, pd.DataFrame)
        assert result.empty

---

## Scorecard

| Criterion | Model A score (1–3) | Model A evidence                                                   | Model B score (1–3) | Model B evidence                                                   |
|-----------|---------------------|--------------------------------------------------------------------|---------------------|--------------------------------------------------------------------|
| line coverage | 2                   | I commented this line of code: open_pressures.drop_duplicates(subset=["x"], inplace=True) and the test didn't fail           | 3                   | Test failed changing each line of the code                         |
| edge-case coverage | 3                   | All edge cases covered                                             | 3                   | All edge cases covered                                             |
| no hardcoded test data | 2                   | Test data is in a separate json file but not in a resources folder | 3                   | Test data is in a separate py file and not in the resources folder |
| same test framework as existing tests | 3                   | Used pytest                                                        | 3                   | Used pytest                                                              |
| **Total** | 10                  |                                                                    | 12                  |                                                                    |

---

## Decision

**Selected model:** Model B

**Rationale:** Model B won because it met the main criterion - line coverage, Model A didn't cover all lines of code

---

## Active Constraint

**What could change this decision within 30 days:**
 Running winning model B for 30 days to write test would give a big cost

---

## Revision history

| Version | Date       | Change                  |
|---------|------------|-------------------------|
| 1.0 | 2026-07-16 | Added Module 020 Kata 1 |