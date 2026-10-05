# CryptoCast: Bitcoin Price Forecasting

I built this project to explore how deep learning handles Bitcoin's rapid market swings across three different forecast horizons: next day (1D), 3 days ahead (3D), and 7 days ahead (7D). Using past daily prices, I set up a 60-day lookback window to feed into multiple neural network setups and evaluated how forecast error scales as we try to predict further into the future.

To keep the pipeline realistic and avoid data leakage, the historical data was split strictly by date (80% train, 20% test) with no shuffling. I benchmarked four architectures—1D-CNN, Simple RNN, Stacked LSTM, and a Transformer with multi-head attention—evaluating each on RMSE, MAE, and MAPE. Overall, the Stacked LSTM caught short-term momentum best, while the 7-day targets showed the expected variance spike that comes with crypto volatility.

### Setup & Run
1. Install dependencies: `pip install -r requirements.txt`
2. Run notebooks in order:
   - `Notebooks/01_data_clean.ipynb`
   - `Notebooks/02_EDA.ipynb`
   - `Notebooks/03_Feature_DL_base.ipynb`