# CIR Yield Curve Reconstruction

This project contains the final notebook for the stochastic interest-rate modelling project. The notebook cleans the yield data, calibrates a Cox-Ingersoll-Ross short-rate model, reconstructs the full yield curve from the 3-month rate, and compares CIR-based extensions using out-of-sample pooled R2.

## Main File

- `yield_curve_prediction.ipynb` - final submission notebook with code, explanations, plots, model comparison, and saved outputs.

## Data Expected

The notebook automatically searches for these files in the current folder or the `data` folder:

- `train_data.csv`
- `test_data.csv`
- `test_data_3M.csv`

During prediction, the notebook uses only `Date` and `ZC025YR` from `test_data_3M.csv`, as required by the problem statement.

## Models Implemented

- Base CIR short-rate model
- CIR++ style median deterministic shift
- Curve-aware affine CIR calibration

The final selected model is the curve-aware affine CIR model because it gives the highest pooled out-of-sample R2.

## Final Score

```text
Curve-Aware Affine CIR    0.891358
CIR++ Median Shift        0.884294
Base CIR                  0.710957
```

The selected model clears the required `R2 > 0.85` threshold.

## Output Files

Running the notebook writes:

- `base_cir_predictions.csv`
- `cirplusplus_predictions.csv`
- `best_cross_sectional_affine_cir_predictions.csv`
- `final_model_comparison.csv`

## How to Run

Open `yield_curve_prediction.ipynb` in Jupyter Notebook, JupyterLab, VS Code, or Google Colab and run all cells from top to bottom.

The notebook includes preprocessing, calibration, evaluation, plots, and CSV export in one file.
