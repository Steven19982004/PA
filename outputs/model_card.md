# Model Card (Short)

## Intended use
Predict next-hour bike rental demand (`cnt`) for operational planning (staffing/rebalancing) under similar city/weather context.

## Not intended use
Not for causal inference, policy fairness claims, or deployment in regions/platforms with materially different demand dynamics.

## Data provenance & constraints
- Source: UCI Bike Sharing hourly data (`hour.csv`) in this local project.
- Leakage controls: dropped `casual` and `registered`; chronological split; pipeline-contained preprocessing.
- Time range includes 2011-01-01 to 2012-12-31 and may not represent future structural changes.

## Evaluation summary
- Selected model: HistGradientBoosting_Fixed
- Test MAE: 61.584
- Test RMSE: 85.961
- Test R2: 0.847

## Caveats and failure modes
Errors vary by hour; extreme demand peaks are harder to predict.
Potential drift risk exists for new mobility policies, shocks, or weather pattern shifts.

## Agent QA note (mistake caught)
An early agent draft of cyclical encoding assumed DataFrame-only inputs and failed when `ColumnTransformer` passed ndarray columns.
This was corrected by deterministic feature-order mapping in `CyclicalEncoder.fit`, followed by full notebook re-execution.
