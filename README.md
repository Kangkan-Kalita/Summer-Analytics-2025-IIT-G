# Summer Analytics 2025 • Consulting & Analytics Club IIT Guwahati

Welcome! This repository chronicles my journey through Summer Analytics 2025 at IIT Guwahati :  
– **Week 1 : Foundations & Tutorials**  
– **Hackathon 1 : Land Cover Classification**  
– **Hackathon 2 : Nutrition Health Survey – Age Prediction**  
– **Capstone Project : Dynamic Urban Parking Pricing System**

---

## 📁 Repo Structure

```
├── week1/
│   ├── notebooks/      ← SA2025_W1.ipynb
│   └── data/           ← Cars.csv
├── First Hackathon/
│   ├── notebooks/      ← 'SA2025Hackathon1.ipynb' & 'Copy of starter-for-hackathon.ipynb' 
│   ├── data/           ← hacktrain/hacktest.csv
│   └── submissions/    ← .csv predictions & submission files
├── hackathon2/
│   ├── notebooks/      ← 'SA2025Hackathon2.ipynb'
│   ├── data/           ← Train_Data.csv, Test_Data.csv, Sample_Submission.csv
│   └── submissions/    ← Couldn't complete this Hackathon, Will update soon!
├── capstone/
│   ├── notebooks/      ← Capstone_Project_SA_2025.ipynb
│   ├── data/           ← dataset.csv, parking_stream_full.csv, parking_stream_final.csv
│   ├── fig & Output/   ← sample plots & dashboards, pricing_results.csv files and a Project Report conatining every little detail in PDF format
│   └── README.md       ← A well explained README file
├── requirements.txt    ← pinned Python packages
└── LICENSE             ← Project license (MIT) 

```


---

# 🗓️ Week 1: Foundations

- **Topics Covered :** Exploratory Data Analysis, Basic Regression & Classification, Pipeline design  
- **Artifacts :**  
  - Jupyter notebooks demonstrating Pandas/EDA
  - Car Model Prediction using basic Data Analysis methods.
   
---

## 🏞️ Hackathon 1 : Land Cover Classification

- **Problem :** Classify satellite tiles into land‐cover categories  
- **Approach :**  
  1. Baseline : Logistic Regression, Random Forest  
  2. Advanced : XGBoost with hyperparameter tuning  
  3. Ensemble : Soft‐voting & stacking  
- **Results :**  
  - Best LB score : ~0.9257 with soft‐voting of top 3  
  - Submissions & code in `First Hackathon`  
- **Key takeaways :**  
  - Importance of feature engineering on spectral bands  
  - Value of ensembling diverse models  

---

## 🍎 Hackathon 2 : Nutrition Health Survey – Age Prediction

- **Problem :** Predict individuals’ age from health & nutrition metrics  
- **Approach :**  
  1. Preprocessing pipeline (imputation, scaling, encoding)  
  2. Baseline : Linear Regression (RMSE ≈ …)  
  3. Advanced : Ridge, Lasso, Random Forest, XGBoost  
  4. Ensembling : Soft voting & stacking  
- **Results :**   
  - Best score : ~0.9112 on test set  
  - Code & submissions in `Second Hackathon`  
- **Key learnings :**  
  - Regularization trade-offs (Ridge vs. Lasso)  
  - Pipeline orchestration with scikit-learn  

---

## 🚗 Capstone : Dynamic Parking Pricing System

**Objective :** Build a real-time pricing engine for 14 urban parking lots using Pathway + Bokeh.  

1. **Data prep**  
   - Combined date/time → Timestamp  
   - Feature engineering : Occupancy Rate, TrafficLevel, VehicleWeight  
2. **Model 1 : Baseline Pricer**  
   - `Priceₜ₊₁ = Priceₜ + α·(Occupancy/Capacity)`, clipped to 0.5×–2× base  
3. **Model 2 : Demand Pricer**  
   - Demand = α·occ_rate + β·(queue/cap) – γ·traffic + δ·is_special + ε·veh_weight  
   - Normalized via `tanh`, then `Price = Base × (1 + λ×Demand)`  
4. **(Optional) Model 3 : Competitive Pricer**  
   - Incorporate nearby lots’ prices (Haversine distance weighting)  
5. **Smoothing & Export**  
   - EMA smoothing to reduce noise  
   - Two-stage CSV :  
     - `parking_stream_full.csv` (raw features)  
     - `parking_stream_final.csv` (with BaselinePrice, DemandPrice, SmoothedDemand)  
6. **Visualization & Dashboard**  
   - Bokeh & Panel tabs → interactive per-lot time series + daily-avg bar charts  
   - Dropdown/slider to switch lots  

**Results :**  
- Baseline vs. Demand price patterns respond to occupancy & queue  
- Smoothed demand yields stable, explainable curves  
- Corr(DemandPrice, OccupancyRate) ≈ 0.63  

**Folder :** `Capstone Project/`  

---

## 🚀 Next Steps & Extras

- **Competitive Model** integration  
- **Hyperparameter tuning** (grid search on α, β, γ, …)  
- **User rerouting suggestions** when lots near capacity  
- **Deploy** Panel dashboard as a simple web app!  

---


## 📧 Contact

Kangkan Kalita • (kalitakangkan.239@gmail.com)
