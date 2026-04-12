# Your Files

Projects include instructor example files that end with `_case`.
Keep these as working examples.

You will generally copy the instructor file, rename it with your alias,
and run your version in addition to the instructor version.

## Choose Your Name (example: `stellar_analytics`)

You may use your real name or any professional alias.
You are **never required to use your real name**.

Naming rules:

- all lowercase
- no spaces (use underscores as needed)

## 1. Python Files

Copy the instructor Python file and rename the copy using your alias.

```text
src/cintel/anomaly_detector_case.py
src/cintel/anomaly_detector_stellar_analytics.py
```

## 2. Python File Execution Command

In your `README.md`, add a line with the execution command just after the instructor command.
Use this command to run your file.

```shell
uv run python -m cintel.anomaly_detector_case
uv run python -m cintel.anomaly_detector_stellar_analytics
```

## 3. Data Files

Copy the instructor data file and rename the copy using your alias.

```text
data/static_data_case.csv
data/static_data_stellar_analytics.csv
```

You may modify the copied dataset as needed for your project,
or choose your own dataset if appropriate.

#  Drift Analysis Documentation

## Datasets Compared

This project compares two datasets:

- **Reference Dataset** (`reference_metrics_case.csv`)
  - Represents historical system behavior
  - Used as the baseline for normal performance

- **Current Dataset** (`current_metrics_case.csv`)
  - Represents recent system behavior
  - Used to detect changes or drift from the baseline

Each dataset includes the following metrics:
- `requests`: number of requests handled
- `errors`: number of failed requests
- `total_latency_ms`: total response time in milliseconds

---

## Drift Indicators Used

Drift was detected using the following indicators:

- **Mean Difference**
  - Calculated as:
    `current average - reference average`
  - Measures how much the system has changed

- **Percentage Difference (Added)**
  - Shows the relative size of the change compared to the baseline
  - Helps interpret whether changes are small or significant

- **Drift Flags**
  - Triggered when the absolute difference exceeds a defined threshold:
    - Requests threshold: 15
    - Errors threshold: 1
    - Latency threshold: 800

---

## Changes Observed

After running the pipeline:

- Differences were observed between current and reference averages
- More drift flags were triggered due to stricter thresholds
- Percentage differences highlighted how large the changes were relative to the baseline
- Some metrics showed noticeable increases or decreases compared to historical behavior

---

## Interpretation of Changes

The observed changes may indicate:

- **Increased requests**
  - Could suggest higher system demand or usage growth

- **Increased errors**
  - May indicate system instability or performance issues

- **Increased latency**
  - Suggests slower response times, which could impact user experience

- **Overall drift**
  - Indicates that the system is no longer behaving like it did during the reference period
  - May require further investigation, scaling, or optimization

---

## Summary

This analysis shows how comparing current system metrics to a historical baseline can help identify meaningful changes in performance. The addition of percentage differences and stricter thresholds improves the ability to detect and interpret drift.
