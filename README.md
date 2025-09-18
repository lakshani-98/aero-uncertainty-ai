# ✈️ PitchGuard: Enhancing Trust in AI for Air Traffic Control  
Uncertainty Estimation in Predictive Models using Monte Carlo Dropout & Deep Ensembles

---

## 🌍 Background
In **Air Traffic Control (ATC)**, machine learning models are increasingly applied for:  
- Aircraft **trajectory prediction**  
- **Conflict detection & resolution**  
- **Delay forecasting**  
- **Anomaly detection**  

While accuracy is important, **uncertainty estimation** is essential in safety-critical systems. Reliable AI should not only predict but also **know when it might be wrong**, allowing human controllers to intervene.  

This project explores **uncertainty-aware AI** methods for ATC, focusing on **aircraft pitch prediction** using **Monte Carlo Dropout (MC Dropout)** and **Deep Ensembles**.  

---

## 🎯 Problem Statement
Current ML models in ATC focus heavily on **prediction accuracy**, neglecting **uncertainty calibration**.  
This increases the risk of **overconfident but wrong predictions**, reducing **trust** in AI systems.  

This project aims to:  
- Provide **well-calibrated uncertainty estimates**  
- Implement **uncertainty-aware rejection** (deferring to humans in high-risk cases)  
- Improve **safety & transparency** in AI-driven ATC systems  

---

## 🔬 Methodology
We implement two uncertainty-aware models for **aircraft pitch prediction**:  

1. **Monte Carlo Dropout (MC Dropout)**  
   - Multiple stochastic forward passes  
   - Mean prediction + standard deviation → **confidence intervals**  

2. **Deep Ensembles**  
   - Train multiple independent networks  
   - Aggregate predictions & model disagreement → **uncertainty estimate**  

### Preprocessing
- Feature standardization (StandardScaler)  
- 80:20 train-validation split  
- Dataset: [Aircraft Pitch Prediction Challenge](https://www.kaggle.com/competitions/pitch-aileron/data)  

### Evaluation Metrics
- **MSE, MAE, R² Score** (accuracy)  
---

## 📊 Results
- Best MC Dropout model (2×128 neurons, dropout=0.2) achieved **R² = 0.86**  
  - 95.9% Prediction Interval Coverage → strong reliability  
- Deep Ensembles achieved **stable, interpretable uncertainty estimates** with low variance  
- Both methods demonstrated **uncertainty-aware rejection**, deferring predictions in risky cases  
