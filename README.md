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

-> Each time series represents a different engine trajectory.

-> Engines start with unknown wear and degrade over time.
-> Training sequences end at failure; test sequences end before failure.
-> Goal: Predict how many cycles remain (RUL) at each test point.

Data includes:

-> 3 operational settings
<ul>21 sensor measurements </ul>
1 unit number and 1 time index per row
