# LSTM for Multivariate Time Series — Predicting Google Stock Prices

This project uses an LSTM-based Recurrent Neural Network to forecast Google’s stock price. The model was trained on five years of historical data to predict price movements over a two-month horizon.

---

## Dataset — [Google Stock (GOOG)](https://finance.yahoo.com/quote/GOOG/history)

The dataset includes daily stock data for Alphabet Inc. (GOOG), sourced from [Yahoo Finance](https://finance.yahoo.com). Each record contains:

- Open  
- High  
- Low  
- Close  
- Adjusted Close  
- Volume  

Timeframes used:

- **Training**: Jan 2019 – June 2023  
- **Validation**: July 2023 – Dec 2023  
- **Testing**: Jan 2024 – Feb 2024  

---

##  Phase 1 — EDA & Preprocessing

### Data Exploration

- Downloaded the full dataset  
- Reviewed summary statistics  
- Cleaned missing values and validated data types  
- Analyzed price trends over time  
- Filtered data based on selected date ranges  
- Saved the filtered version locally  

### Data Preparation

- Reloaded filtered data  
- Confirmed column types  
- Selected features and target labels  
- Split into training, validation, and test sets  
- Normalized values using [`MinMaxScaler`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html)  
- Saved preprocessed datasets  

---

##  Phase 2 — Model Training & Prediction

### Model Architecture

Built using [`TensorFlow`](https://www.tensorflow.org/api_docs/python/tf/keras/Sequential) Sequential API:

- Input layer  
- 4× [`LSTM`](https://www.tensorflow.org/api_docs/python/tf/keras/layers/LSTM) layers (100 units each)  
- 4× [`Dropout`](https://www.tensorflow.org/api_docs/python/tf/keras/layers/Dropout) layers (rate = 0.2)  
- Final [`Dense`](https://www.tensorflow.org/api_docs/python/tf/keras/layers/Dense) output layer (1 unit)

### Training Configuration

- Optimizer: [`Adam`](https://www.tensorflow.org/api_docs/python/tf/keras/optimizers/Adam)  
- Loss: [`MeanSquaredError`](https://www.tensorflow.org/api_docs/python/tf/keras/losses/MeanSquaredError)  
- Epochs: 200  
- Batch size: 64  

### Steps

- Loaded preprocessed datasets  
- Created input sequences  
- Compiled and trained the LSTM model  
- Evaluated training and validation loss  
- Predicted prices on all data segments  
- Applied inverse scaling for real-world values  
- Visualized predictions  

---
