LSTM-Based Multivariate Time Series for Stock Price Prediction

This project uses an LSTM-based Recurrent Neural Network to forecast stock prices. The model was trained on five years of Google (Alphabet Inc.) stock data to predict price movements over a two-month horizon.

Dataset: Google Stock (GOOG)

The data comes from Yahoo Finance and includes daily records of Alphabet Inc.’s stock, covering these fields: open, high, low, close, adjusted close, and trading volume.

After an initial exploration of the full dataset, we narrowed it down to three distinct timeframes:

Training: Jan 2019 – June 2023

Validation: July 2023 – Dec 2023

Testing: Jan 2024 – Feb 2024

Phase 1: Exploration & Preprocessing
Exploratory steps:

Pulled and loaded the raw data

Reviewed summary stats and trends

Cleaned up missing or misformatted entries

Analyzed time-based patterns

Filtered the dataset to the selected date ranges

Saved the filtered version locally

Preprocessing tasks:

Reloaded the filtered data

Ensured proper data types

Picked features and labels

Split data into training, validation, and test sets

Normalized values to the [0, 1] range using MinMaxScaler

Saved the processed datasets to local storage

Phase 2: Model Training & Prediction
Training and prediction steps:

Loaded preprocessed data

Built input sequences for LSTM

Defined the model in TensorFlow as follows:

Input layer

4 LSTM layers (each with 100 units)

4 Dropout layers (0.2 rate)

Final Dense layer (1 unit)

Compiled the model with Adam optimizer and MSE loss

Trained the model for 200 epochs with a batch size of 64

Tracked training and validation loss

Generated predictions for all three time segments

Reversed the scaling to get predictions in actual price terms

Plotted and reviewed the results
