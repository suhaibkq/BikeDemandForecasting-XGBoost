# 🚴‍♂️ Forecasting Bike Sharing Demand with XGBoost

## 📌 Problem Statement

Bike-sharing platforms need to efficiently predict rental demand to optimize operations, redistribute bikes, and plan for peak usage hours. This project involves building a machine learning model to forecast hourly bike rental demand using historical data.

## 🎯 Objective

To develop an accurate regression model using XGBoost that forecasts the hourly count of total bike rentals. The model is trained on weather, time, and season-related features and tested on a hold-out period.

## 📊 Dataset

- **Files**: `train.csv`, `test.csv` (originally from Kaggle's [Bike Sharing Demand competition](https://www.kaggle.com/c/bike-sharing-demand/data))
- **Target Variable**: `count` — number of total rentals (registered + casual)
- **Key Features**:
  - Temporal: `year`, `month`, `day`, `hour`, `dayofweek`
  - Weather: `temp`, `atemp`, `humidity`, `windspeed`, `weather`
  - Indicators: `season`, `holiday`, `workingday`

## 📁 Project Structure

├── 1-biketrain-data_preparation.ipynb # Data exploration and preprocessing
├── 2-biketrain-xgboost_training.ipynb # Model building and training using XGBoost
├── 3-biketrain-xgboost_prediction.ipynb # Model prediction and submission file generation
├── train.csv
├── test.csv
├── README.md


## 🧪 Project Workflow

1. **Data Preparation**
   - Combined datetime components into new features (year, month, hour, dayofweek)
   - Removed outliers and performed log transformation on skewed variables
   - Split data into training and validation sets (first 19 days for training, rest for testing)

2. **Model Training**
   - Used **XGBoost Regressor** for superior performance on tabular data
   - Tuned hyperparameters like learning rate, max_depth, and n_estimators
   - Applied early stopping using validation loss

3. **Evaluation**
   - Metrics used: **Root Mean Squared Logarithmic Error (RMSLE)**
   - Feature importance analysis
   - Final predictions were converted back from log scale

## 🏆 Results

- **Best RMSLE Score**: ~X.XXX on validation set
- **Top Features**: `hour`, `temp`, `humidity`, `workingday`, `windspeed`
- **Observations**:
  - Demand peaks around 8am and 5-6pm (commute times)
  - Weather and holiday indicators significantly influence rental counts

## 🔍 Key Takeaways

- Combining temporal and weather features improves model accuracy
- XGBoost handles non-linear patterns and feature interactions well
- Log transformation on skewed target variable improves model stability

## 🚀 Future Enhancements

- Deploy model as a REST API using Flask or FastAPI
- Automate real-time data ingestion and forecasting pipeline
- Experiment with LSTM or Prophet for time series modeling

## 👨‍💻 Author

**Suhaib Khalid**  
ML Enthusiast

