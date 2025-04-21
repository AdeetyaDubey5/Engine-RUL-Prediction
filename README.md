# Engine-RUL-Prediction

## RUL Prediction on CMAPSS Dataset using LSTM & GRU
This project predicts the Remaining Useful Life (RUL) of jet engines using deep learning models — LSTM and GRU — on the CMAPSS FD001 dataset. The models are trained on multivariate time series data to estimate how many cycles remain before engine failure.

### 📊 Dataset Overview
Provided by NASA’s Prognostics Center of Excellence, the CMAPSS dataset includes four subsets:

Dataset	Train Engines	Test Engines	Conditions	Fault Modes
FD001	100	100	1       (Sea Level)	1 (HPC Degradation)
FD002	260	259	6	1 (HPC Degradation)
FD003	100	100	1 (Sea Level)	2 (HPC, Fan Degradation)
FD004	248	249	6	2 (HPC, Fan Degradation)

Each engine runs from a healthy state to system failure. The objective is to predict RUL from a given point in time using sensor and setting data.

### 🔬 Experimental Scenario

* Each time series represents a different engine trajectory.

* Engines start with unknown wear and degrade over time.

* Training sequences end at failure; test sequences end before failure.

* Goal: Predict how many cycles remain (RUL) at each test point.

Data includes:

* 3 operational settings

* 21 sensor measurements 

* 1 unit number and 1 time index per row

### 🤖 Models Used

We implemented two deep learning models for RUL regression:

#### ✅ LSTM

* Captures long-term dependencies in sequential sensor data.

* Performs better in modeling engine degradation patterns.

#### ✅ GRU

* More efficient with fewer parameters.

* Faster to train but slightly less accurate in this task.

### 📈 Performance Comparison

The performance of the models was evaluated using three key metrics: Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Error (MAE). These metrics provide insight into the accuracy of the predictions made by each model, allowing for a comprehensive comparison of their effectiveness in predicting RUL.

|     Model     |      MSE      |      RMSE      |      MAE      |
| ------------- | ------------- |  ------------- | ------------- |
|     LSTM      |   242.34      |    15.57       |    11.26      |
|     GRU       |   365.82      |    19.13       |    13.91      |


### 🧠  Conclusion

In this project, we successfully explored the use of deep learning for Remaining Useful Life (RUL) prediction using the CMAPSS FD001 dataset. Two sequence models — LSTM and GRU — were developed and compared on their ability to learn degradation patterns from multivariate sensor data.

The LSTM model consistently outperformed the GRU model across all metrics (MSE, RMSE, MAE), highlighting its strength in capturing long-term dependencies and subtle trends in time series data. GRU, while faster and more efficient, showed slightly lower accuracy.

This experiment demonstrates that LSTM networks are better suited for complex prognostics tasks like RUL prediction where understanding temporal evolution is crucial. The findings also underline the potential of deep learning methods to support predictive maintenance in industrial applications by providing reliable failure predictions based on sensor signals.
