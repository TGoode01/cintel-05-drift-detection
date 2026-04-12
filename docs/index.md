# Continuous Intelligence

This site provides documentation for this project.
Use the navigation to explore module-specific materials.

## How-To Guide

Many instructions are common to all our projects.

See
[⭐ **Workflow: Apply Example**](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
to get these projects running on your machine.

## Project Documentation Pages (docs/)

- **Home** - this documentation landing page
- **Project Instructions** - instructions specific to this module
- **Your Files** - how to copy the example and create your version
- **Glossary** - project terms and concepts

## Additional Resources

- [Suggested Datasets](https://denisecase.github.io/pro-analytics-02/reference/datasets/cintel/)

## Custom Project

### Dataset

I used two datasets in this project:

- **Reference dataset** (`reference_metrics_goode.csv`)
  - This shows how the system normally performs
  - It acts as the baseline

- **Current dataset** (`current_metrics_goode.csv`)
  - This shows the system’s more recent performance
  - I compare this to the reference data to see if anything has changed

Both datasets include:
- requests (how many requests were handled)
- errors (how many failed)
- total_latency_ms (how long responses took)

---

### Signals

I used a few main signals to compare the datasets:

- Average requests
- Average errors
- Average latency

From these, I also created:

- **Difference values**
  - Shows how much the current data changed compared to the reference data

- **Percentage change**
  - Helps show how big the change is in a more understandable way

- **Drift flags**
  - These turn on when a change is bigger than the set limit:
    - Requests: 15
    - Errors: 1
    - Latency: 900

---

### Experiments

I made a couple of changes to improve the drift detection:

- Lowered the thresholds so the system could catch smaller changes
- Added percentage calculations to better understand how big the changes are
- Added a check to make sure there were no missing values before running the analysis
- Updated the output file to include the new metrics

---

### Results

After running the updated version:

- More drift flags showed up because the thresholds were stricter
- The percentage changes made it easier to see how much things changed
- The program ran successfully without errors
- The output file now includes more useful information

---

### Interpretation

From the results, I can see that the system has changed compared to before.

What this might mean:

- If requests increased, it could mean more users or higher demand
- If errors increased, it could mean something in the system is not working as well
- If latency increased, it could mean the system is slower than before

Overall, the system is not behaving exactly like it used to, which means something may need attention or further investigation.
