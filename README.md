# Stock Price Prediction using LSTM Models

## Dataset Acquisition
The first step in this project was acquiring historical data of closing prices for both companies (Apple and Amazon). Using the Yahoo Finance API, **`yfinance`**, we extracted the dataset for both companies for the last 5 years and plotted them to analyze and visualize trends.

## Data Preprocessing
- **Data Cleaning & Training Set Creation**: We cleaned the dataset and focused on the closing stock prices. The data was split into **80% training** and **20% testing** datasets.
- **Scaling & Reshaping**: 
   - The stock price data was scaled between **0 and 1**.
   - Two NumPy arrays were created:
     - The first array contained stock prices for the past 60 days (e.g., day 0 to 59).
     - The second array contained the value to be predicted (e.g., the 60th day).
   - The data was reshaped into a **three-dimensional array** for the LSTM model.

## Model Training
Two LSTM model architectures were tested:

1. **First Model Architecture**:
   - 4 LSTM layers with **100 output units**.
   - First 3 layers returned sequences, while the last layer acted as the output layer.
   - **Dropout layers** (rate of 0.5) were added to prevent overfitting.
   - A **Dense (Fully Connected) layer** was included to process output.

2. **Second Model Architecture**:
   - 2 LSTM layers, 2 Dense layers, and Dropout layers.

Both models were trained with a **batch size of 32** and **100 epochs**, and evaluated using the **root mean square error (RMSE)**.

## Model Evaluation
- A testing dataset was created similarly to the training dataset.
- **Predictions** were made on the testing data and rescaled to their original form.
- **RMSE Calculation**: The difference between predicted and actual values was used to calculate the RMSE.

## Analysis and Conclusion
- **Data Visualization**: The stock market trends were visualized to train the model effectively. Below are the trend graphs for **Apple** and **Amazon** stock prices.


- **Model Performance**:
  - **Model 1 RMSE**: ~0.8364
  - **Model 2 RMSE**: ~2.817
  
These values indicate relatively accurate results.
