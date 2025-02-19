# Model Definition and Evaluation

**[Notebook](model_tree.ipynb)**

## Advanced models Explored

### 1. Traditional Time Series Models

- ARIMA: Best order found was (2,0,1)x(0,0,1,12h), but performance was slightly worse than naive.

- ARIMA-X: Attempted to include exogenous features but faced implementation challenges.

### 2. Tree-Based Models

- Random Forest: Best parameters: max_depth=10, n_estimators=50. Achieved best performance.

- XGBoost: Best parameters: max_depth=5, n_estimators=200, colsample_bytree=0.8, subsample=0.8.

### 3. Neural Networks

- GRU: RMSE: 23.8, MAPE: 14.3%

- LSTM: RMSE: 18.3, MAPE: 12.7%

- N-Hits: RMSE: 23.8, MAPE: 14.9%

### 4. Chronos - Pretrained Forecasting Model

- Zero-shot performance: RMSE: 27.0, MAPE: 17.0%

- Fine-tuning results: No significant improvement over zero-shot.

## Discussion

- Most models performed only slightly better than the naive baseline.

- Tree-based models (Random Forest, XGBoost) achieved the best results.

- Deep learning models (LSTM, GRU, N-Hits) performed worse than tree-based models.

- Chronos (zero-shot) performed comparably to naive forecasting.
