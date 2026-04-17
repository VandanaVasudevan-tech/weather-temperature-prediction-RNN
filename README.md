# weather-temperature-prediction-RNN
A deep learning-based time-series forecasting project using SimpleRNN to predict daily temperatures. The pipeline includes data preprocessing, normalization, sequence modeling, model evaluation, and multi-step future prediction with clear visual insights.


# 🌦️ Weather Temperature Prediction using SimpleRNN

## 📌 Project Overview

This project implements a **time-series forecasting model** using a **Simple Recurrent Neural Network (SimpleRNN)** to predict daily temperatures based on historical weather data.

The notebook covers the **complete machine learning pipeline** — from data preprocessing to model training, evaluation, and future forecasting.

---

## 🎯 Objective

* Predict **next day temperature** using past weather data
* Learn temporal patterns using **sequence modeling (RNN)**
* Forecast **next 7 days temperature** using trained model

---

## 📂 Dataset Details

The dataset contains daily weather observations with the following features:

* 📅 Date
* 🌡️ Temperature *(Target variable)*
* 💧 Humidity
* 🌬️ Wind Speed

---

## ⚙️ Workflow Explained

### 🔹 1. Data Loading & Exploration

* Loaded dataset using pandas
* Converted `Date` column to datetime format
* Sorted data in chronological order
* Displayed first few rows
* Visualized temperature trends over time

---

### 🔹 2. Data Preprocessing

* Checked and handled missing values
* Selected relevant features:

  * Temperature
  * Humidity
  * Wind Speed
* Applied **MinMaxScaler** to normalize data

---

### 🔹 3. Sequence Creation (Core RNN Logic)

* Created input sequences of **past 7 days**
* Each sequence contains:

  * Temperature
  * Humidity
  * Wind Speed
* Target = **next day temperature**

👉 This transforms data into **(samples, timesteps, features)** format required for RNN.

---

### 🔹 4. Train / Validation / Test Split

* 70% → Training
* 15% → Validation
* 15% → Testing

⚠️ Data is split **sequentially (no shuffling)** to preserve time order.

---

### 🔹 5. Model Architecture

The model is built using TensorFlow/Keras:

* SimpleRNN layer (32 units)
* Dropout layer (0.2) → prevents overfitting
* Dense layer (1 unit) → output temperature

---

### 🔹 6. Model Compilation

* Loss Function: **Mean Squared Error (MSE)**
* Optimizer: **Adam**
* Metric: **Mean Absolute Error (MAE)**

---

### 🔹 7. Model Training

* Epochs: up to 50
* Batch Size: 32
* Used **Early Stopping** to stop training when validation loss stops improving

📉 Plotted:

* Training Loss
* Validation Loss

---

### 🔹 8. Model Evaluation

Predictions are made on the test dataset and evaluated using:

* 📉 RMSE (Root Mean Squared Error)
* 📊 MAE (Mean Absolute Error)
* 📈 R² Score

Also visualized:

* **Actual vs Predicted temperatures** using date-based plots

---

### 🔹 9. Future Forecasting (Next 7 Days)

* Used last 7 days of data as input

* Applied **rolling prediction approach**:

  * Predict next value
  * Add it back to input
  * Repeat for 7 steps

* Converted predictions back to original scale

* Generated **future dates**

* Plotted:

  * Recent actual values
  * Future predicted temperatures

---

## 📊 Output Visualizations

The notebook includes:

* Temperature trend over time
* Training vs validation loss curve
* Actual vs predicted temperature graph
* Next 7 days forecast plot (with dates on x-axis)

---

## 🧠 Key Concepts Demonstrated

* Time-series data preprocessing
* Sequence generation for RNN
* SimpleRNN architecture
* Model training with validation
* Performance evaluation metrics
* Multi-step forecasting

---

## ⚠️ Observations

* Model captures **short-term trends** effectively
* Predictions are **smooth**, indicating:

  * Limited ability of SimpleRNN to capture long-term seasonality

---

## 🚀 Possible Improvements

* Replace SimpleRNN with:

  * LSTM
  * GRU
* Increase sequence length
* Add more features (pressure, rainfall, etc.)
* Perform hyperparameter tuning

---

## 🛠️ Technologies Used

* Python
* Pandas, NumPy
* Matplotlib
* Scikit-learn
* TensorFlow / Keras

---

## 📌 Conclusion

This project demonstrates how a **SimpleRNN model can be used for time-series forecasting**. It successfully predicts temperature trends and performs multi-step forecasting, while also highlighting the limitations of basic RNN models.

---

## ▶️ How to Run

1. Clone the repository
2. Install required libraries:

   ```bash
   pip install pandas numpy matplotlib scikit-learn tensorflow
   ```
3. Run the Jupyter Notebook

---

