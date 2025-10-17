# SignalSanitizer: Ensemble Denoising with Huber & Ridge

## Short Description
An end-to-end pipeline that denoises fixed-length 1D signals using preprocessing (QuantileTransformer, RobustScaler, PowerTransformer) and an ensemble of HuberRegressors and RidgeRegressors. The notebook performs EDA on noise characteristics, trains per-column regressors, ensembles predictions, and writes submission-ready CSVs.

## Motivation
Real-world signals often contain complex, non-Gaussian noise and outliers. This project focuses on robust regression techniques and careful preprocessing to recover clean signals from noisy observations. The approach favors classical, interpretable models (Huber and Ridge) combined with strong feature scaling and distributional transforms for stability.

## Repository Structure
```
24_part1.ipynb            # Main exploratory notebook + model pipeline (provided)
/data                     # (optional) raw and processed datasets
/outputs                  # (optional) generated CSVs and model artifacts
/README.md                # This file
/requirements.txt         # Python package dependencies (suggested)
```

## Dataset
Developed using the AFML assignment dataset (train/test CSVs). Signals are reshaped to a 2D array where each sample contains 20 sequential values.

## Pipeline Overview
1. Exploratory Data Analysis (EDA)
2. Preprocessing: QuantileTransformer, PowerTransformer, RobustScaler
3. Modeling: HuberRegressor + RidgeRegressor Ensemble
4. Postprocessing: Inverse-transform predictions and generate CSV

## Evaluation Metrics
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)

## How to Run Locally
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
jupyter lab
```
Edit paths in `24_part1.ipynb` to match your dataset.

## Suggested Requirements
```
pandas
numpy
scikit-learn
scipy
matplotlib
seaborn
```

## Future Improvements
- Add tree-based or deep learning models for non-linear noise
- Automate hyperparameter tuning
- Use stacking instead of simple averaging
- Implement model persistence (joblib)

## License
MIT License (or add your preferred license)
