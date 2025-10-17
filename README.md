# RobustSignalDenoiser-Huber-Ridge-Ensemble
An end-to-end pipeline that denoises fixed-length 1D signals using preprocessing (QuantileTransformer, RobustScaler, PowerTransformer) and an ensemble of HuberRegressors and RidgeRegressors. The notebook performs EDA on noise characteristics, trains per-column regressors, ensembling predictions, and writes submission-ready CSVs.
