# ⚙️ Predictive Maintenance System using IoT Sensor Data

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat-square&logo=scikit-learn)
![Random Forest](https://img.shields.io/badge/Model-Random%20Forest-green?style=flat-square)
![LSTM](https://img.shields.io/badge/Model-LSTM-purple?style=flat-square&logo=tensorflow)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

> Predicting industrial equipment failures before they happen — using NASA turbofan sensor data, ensemble ML models, and achieving **91% precision** with failures detected **10+ cycles in advance**.

---

## 📌 Project Overview

This project builds a **Predictive Maintenance (PdM)** system that forecasts the **Remaining Useful Life (RUL)** of industrial turbofan engines using multivariate IoT sensor data. It simulates a real-world industrial ML pipeline — from raw sensor signal analysis to an ensemble model that maintenance teams can act on.

---

## 🎯 Business Objectives

- Replace reactive (break-fix) maintenance with proactive, data-driven maintenance
- Predict equipment failure 10+ operational cycles before it occurs
- Reduce unplanned downtime and maintenance costs
- Deliver interpretable feature importance insights to maintenance engineers

---

## 🗂️ Dataset

| Detail | Info |
|---|---|
| Source | [NASA CMAPSS Turbofan Engine Dataset](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps) |
| Records | 20,000+ multivariate sensor readings |
| Sensors | 21 sensor measurements per reading |
| Task | Regression — predict RUL (cycles remaining) |

The dataset simulates run-to-failure trajectories of turbofan engines under different operating conditions and fault modes.

---

## 🔧 Tech Stack

| Layer | Tools |
|---|---|
| Data Processing | Python (Pandas, NumPy) |
| Machine Learning | Scikit-learn (Random Forest), XGBoost |
| Deep Learning | Keras / TensorFlow (LSTM) |
| Visualization | Seaborn, Matplotlib |
| Environment | Jupyter Notebook, Google Colab |

---

## 📊 Methodology

### 1. 🔍 Exploratory Data Analysis
- Analysed sensor degradation trends across engine life cycles
- Identified high-signal vs. low-variance sensors for feature selection
- Visualised multivariate time-series patterns per engine unit

### 2. 🛠️ Feature Engineering
- Constructed rolling mean and standard deviation features (window sizes: 5, 10, 30 cycles)
- Added lag features to capture temporal degradation patterns
- Normalised sensor readings using Min-Max scaling per operating condition

### 3. 🤖 Model Training & Benchmarking

| Model | RMSE | Precision (failure ≤ 10 cycles) |
|---|---|---|
| Baseline (Linear Regression) | — | — |
| Random Forest | Lower | High |
| XGBoost | Lower | High |
| LSTM | Lower | High |
| **Ensemble (RF + XGBoost + LSTM)** | **Lowest** | **91%** |

The ensemble approach combined predictions via **weighted averaging**, achieving the best generalisation.

### 4. 📉 Model Evaluation
- Metrics: RMSE, MAE, R²
- Classification threshold: Engines with predicted RUL ≤ 10 cycles flagged as "At-Risk"
- Confusion matrix and Precision/Recall analysis for the binary failure classification task

---

## 💡 Key Results

- 🎯 **91% precision** in predicting failures 10+ cycles in advance
- 📉 Ensemble model significantly outperformed single-model baselines on RMSE
- 🔬 Top 5 most predictive sensors identified via feature importance (Random Forest)
- 📊 Degradation curves clearly visualised — sensor signals deteriorate non-linearly near failure

---

## 📐 Visualizations Produced

| Chart | Insight |
|---|---|
| Sensor degradation over time | Shows which sensors degrade closest to failure |
| Feature importance bar chart | Ranks which signals matter most for RUL prediction |
| RUL prediction vs. actual | Model output vs. ground truth per engine unit |
| Confusion matrix | Precision/Recall for binary At-Risk classification |

---

## 📁 Repository Structure

```
📦 predictive-maintenance-iot
 ┣ 📂 notebooks
 ┃ ┣ 01_eda_sensor_analysis.ipynb
 ┃ ┣ 02_feature_engineering.ipynb
 ┃ ┣ 03_model_training.ipynb
 ┃ └── 04_ensemble_evaluation.ipynb
 ┣ 📂 data
 ┃ └── (download from Kaggle — link above)
 ┣ 📂 models
 ┃ └── ensemble_model.pkl
 ┣ requirements.txt
 └── README.md
```

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/fitloopmodels/predictive-maintenance-iot.git
cd predictive-maintenance-iot

# 2. Install dependencies
pip install -r requirements.txt

# 3. Download NASA CMAPSS dataset and place in /data

# 4. Run notebooks in order (01 → 02 → 03 → 04)
jupyter notebook
```

---

## 🔭 Future Improvements

- [ ] Deploy model as a REST API using FastAPI
- [ ] Add real-time sensor streaming simulation
- [ ] Experiment with Transformer-based time-series models
- [ ] Build an interactive Streamlit dashboard for maintenance teams

---

## 📬 Contact

**Siva Prasath V M**
📧 sivaprasath.vm2003@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/sivaprasathvm)
💻 [GitHub](https://github.com/fitloopmodels)
