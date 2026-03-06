# PA Coursework: Hourly Bike Demand Prediction

This repository contains an end-to-end predictive analytics workflow for forecasting hourly bike rental demand (`cnt`) using the UCI Bike Sharing hourly dataset.

## 1. Project objective
- Predict next-hour bike rental demand for operational planning.
- Follow a reproducible ML pipeline: problem framing -> EDA -> preparation -> modelling -> evaluation -> final narrative.
- Prevent leakage and keep a strict chronological validation design.

## 2. Repository structure
- `PA_MachineLearning_BikeSharing.ipynb`: main notebook (single entry point).
- `Raw_Data/hour.csv`: dataset used in the project.
- `figures/`: generated plots used in the report.
- `figures/table_shots/`: Python-rendered table screenshots used in the report.
- `outputs/`: exported metrics, diagnostics, logs, and model card.
- `models/final_model.joblib`: serialized final model.
- `requirements.txt`: Python dependencies.
- `README_run.md`: compact run checklist.

## 3. Environment setup
From the project directory:

```bash
cd ~/Desktop/PA_coursework
python3 -m pip install -r requirements.txt
```

## 4. How to run
Start Jupyter and run all notebook cells in order:

```bash
jupyter notebook PA_MachineLearning_BikeSharing.ipynb
```

Then choose: `Kernel -> Restart Kernel and Run All Cells`.

## 5. Reproducibility controls
- Random seed fixed at `42`.
- Chronological split (train/validation/test) with split audit export.
- Leakage columns (`casual`, `registered`) excluded from predictors.
- Preprocessing and models wrapped in scikit-learn pipelines.

## 6. Key exported outputs
Generated in `outputs/`:
- `split_audit.csv`
- `data_validation_checks.csv`
- `baseline_metrics.csv`
- `validation_metrics.csv`
- `test_metrics.csv`
- `test_predictions.csv`
- `hourly_error_metrics.csv`
- `error_peak_vs_nonpeak.csv`
- `error_by_weathersit.csv`
- `top15_feature_importance.csv`
- `ann_cv_top_results.csv`
- `final_model_summary.json`
- `model_card.md`
- `agent_step_verification_log.csv`
- `agent_interaction_log_export.csv`
- `report_tables_black_header.xlsx`

Generated in `figures/`:
- EDA plots
- model comparison plots
- residual and failure-mode diagnostics
- report table screenshots (`figures/table_shots/`)

## 7. Final report file
Current revised report draft:
- `/Users/cai/Desktop/PA-Coursework-文字-REVISED.docx`

## 8. Notes for markers
- The notebook is the authoritative source for all metrics and figures.
- The report references only artifacts that can be traced to files in this repository.
