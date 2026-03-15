#  Energy Demand Forecasting using LSTM

##  Project Overview

Energy demand forecasting is an important task for power system planning and energy management. Accurate predictions help utilities balance electricity supply and demand, reduce operational costs, and improve grid reliability.

This project builds a **deep learning based time-series forecasting system** using **Long Short-Term Memory (LSTM)** networks to predict future electricity demand from historical consumption data.

The trained model learns temporal patterns in energy usage and forecasts **future energy demand for the next 30 days**. An **interactive Streamlit dashboard** is used to visualize predictions along with historical demand.

---

##  Objectives

* Forecast electricity demand for the **next 30 days**
* Capture temporal patterns in energy consumption using **LSTM**
* Visualize **historical and predicted energy demand**
* Deploy the forecasting system using **Streamlit**

---

##  Model Used

### Long Short-Term Memory (LSTM)

LSTM is a type of **Recurrent Neural Network (RNN)** designed for sequential and time-series data. It is capable of learning **long-term dependencies and temporal patterns**, making it well suited for forecasting tasks such as energy demand prediction.

The model takes a sequence of previous time steps as input and predicts future energy demand values.

---

##  Model Performance

| Model        | RMSE       |
| ------------ | ---------- |
| ARIMA        | 1223.59    |
| SARIMA       | 5115.53    |
| Holt-Winters | 985.99     |
| Prophet      | 819.20     |
| **LSTM**     | **100.06** |
| Transformer  | 279.28     |

The **LSTM model achieved the best performance**, producing the lowest forecasting error.

---

## 🛠 Technologies Used

* Python
* TensorFlow / Keras
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Streamlit

---

##  Project Structure

```
energy-demand-forecasting-lstm
│
├── app.py                # Streamlit application
├── lstm_model.h5         # Trained LSTM model
├── scaler.pkl            # Feature scaler
├── metrics.pkl           # Model evaluation metrics
├── last_sequence.npy     # Last sequence used for forecasting
├── last_date.pkl         # Last timestamp in dataset
├── history.pkl           # Historical energy data for visualization
│
└── README.md
```

---

##  How the Forecasting Works

1. Historical energy demand data is preprocessed and feature engineered.

2. Time-related features such as:

   * Hour
   * Day
   * Month
   * Day of week
   * Weekend indicator
   * Seasonal encoding

   are added to improve prediction accuracy.

3. Data is scaled using **MinMaxScaler**.

4. The LSTM model is trained using sequences of previous time steps.

5. During prediction:

   * The last known sequence is used as input
   * Future timestamps are generated
   * The model predicts demand step-by-step for future hours

6. Predictions are **inverse transformed** to obtain real energy demand values.

---

##  Streamlit Dashboard Features

The deployed dashboard provides:

* Interactive **energy demand forecasting**
* User selection for **number of forecast days**
* Visualization of **historical vs predicted demand**
* Display of **model performance metrics**
* Downloadable **forecast results as CSV**

---

##  Running the Project

### 1️ Clone the repository

```bash
git clone https://github.com/yourusername/energy-demand-forecasting-lstm.git
cd energy-demand-forecasting-lstm
```

### 2️ Install dependencies

```bash
pip install -r requirements.txt
```

### 3️ Run the Streamlit app

```bash
streamlit run app.py
```

---

##  Example Output

The dashboard displays:

* Historical electricity demand
* Forecasted demand for upcoming days
* Model performance metrics

The forecast graph clearly shows **past demand trends and future predictions**.

---

##  Future Improvements

* Add **weather data integration**
* Implement **attention-based transformer models**
* Perform **hyperparameter optimization**
* Deploy the application on **Streamlit Cloud**

---

##  Conclusion

This project demonstrates how **deep learning models like LSTM can effectively capture temporal patterns in energy consumption data and generate accurate forecasts**. The integration with **Streamlit** provides an interactive interface for visualizing and analyzing future energy demand.

---

##  Author

Developed as a **Data Science and Deep Learning project** for energy demand forecasting using LSTM.

---
