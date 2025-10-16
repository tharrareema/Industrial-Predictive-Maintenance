## Predictive Maintenance System for Industrial Assets

### 🧠 Project Title
**Remaining Useful Life (RUL) Prediction for Turbofan Engines**

### 📘 Project Description
Developed a predictive maintenance system using time-series sensor data from turbofan engines. The model predicts **Remaining Useful Life (RUL)** before failure, enabling **condition-based maintenance** and reducing unplanned downtime.

### 🎯 Business Task
- Predict RUL in operational cycles for each asset  
- Reduce unplanned maintenance costs  
- Optimize replacement parts inventory  

### 📁 Dataset Summary

| Feature | Description |
|---------|-------------|
| ⚙️ Operational Settings | 3 operational variables per usage scenario |
| 📊 Sensor Measurements | 21 sensor channels (e.g., turbine speed, fan temperature) |
| 🕒 Temporal | Cycle ID (time until failure) |
| 🎯 Target | Remaining Useful Life (RUL) |

**Data Source:** NASA C-MAPSS dataset

### 🧰 Tools & Technologies
Python • TensorFlow / Keras • Pandas • NumPy • Scikit-learn

### 🧹 Data Cleaning & Preparation
- **RUL Derivation:** RUL = final cycle – current cycle  
- **Noise Reduction:** Rolling mean / median smoothing  
- **Feature Scaling:** MinMaxScaler for LSTM stability  
- **Sequence Windowing:** Fixed-length sequences (e.g., 50 cycles) for LSTM input  

### 📊 Model Architecture & Performance
- **Chosen Model:** LSTM / GRU  
- **Architecture:**  
  - Input: 50 time steps, 14 sensor features  
  - LSTM/GRU Layer 1: 100 units, return sequences  
  - LSTM/GRU Layer 2: 50 units, return last output  
  - Dropout Layer: Prevent overfitting  
  - Dense Output: Linear activation predicting RUL  
- **Performance Metrics:**  
  - RMSE: 18.5 RUL cycles  
  - C-MAPSS Score: 245  

### 💡 Strategic Recommendations
- Deploy LSTM/GRU for non-linear degradation prediction  
- Trigger alerts at thresholds (RUL < 50 cycles)  
- Schedule retraining pipelines with new operational data  

</details>

---
