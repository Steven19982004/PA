# How to run the notebook

## 1) Open project
Change to the project directory:

```bash
cd ~/Desktop/PA_coursework
```

## 2) Install dependencies

```bash
pip install -r requirements.txt
```

## 3) Start Jupyter and run all

```bash
jupyter notebook PA_MachineLearning_BikeSharing.ipynb
```

Then in Jupyter: **Kernel -> Restart Kernel and Run All Cells**.

## 4) Where outputs are saved
- Figures (PNG): `./figures/`
- Model artifact: `./models/final_model.joblib`
- Tables/predictions: `./outputs/`
  - `split_audit.csv`
  - `validation_metrics.csv`
  - `test_metrics.csv`
  - `test_predictions.csv`
  - `hourly_error_metrics.csv`
  - `top15_feature_importance.csv` (if model supports feature attribution)
  - `final_model_summary.json`

## Notes
- The notebook enforces time-aware split and avoids leakage (`casual`, `registered` dropped from features).
- Random seed is fixed for reproducibility.
