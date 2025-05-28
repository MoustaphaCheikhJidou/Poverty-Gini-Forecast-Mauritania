# Poverty & Inequality Forecasting in Mauritania
## 📖 Abstract

Poverty remains a critical challenge for Mauritania’s socio-economic development. This project models and forecasts four key indicators—poverty headcount (P0), poverty gap (P1), poverty severity (P2) and the Gini index—over 1996–2030. We interpolate quad-annual survey data (2000, 2004, 2008, 2014, 2019) into annual series via cubic splines, then fit polynomial trends (degrees 1–3), choosing the best by Akaike’s Information Criterion (AIC), and evaluate forecast accuracy using RMSE, MAE, MAPE and Theil’s U :contentReference[oaicite:0]{index=0}.

## 📝 Introduction

Understanding and anticipating poverty trends is vital for evidence-based policy. This report constructs and forecasts:

- **P0** – incidence (headcount) of poverty  
- **P1** – depth (gap) of poverty  
- **P2** – severity of poverty  
- **Gini index** – income inequality  

using ANSADE survey data interpolated into annual series (1996–2024) and polynomial forecasting to 2030 :contentReference[oaicite:1]{index=1}.

---

## 📚 Data & Methodology

- **Data source:** Enquête Permanente sur les Conditions de Vie (EPCV) – years 2000, 2004, 2008, 2014, 2019 via ANSADE.  
- **Interpolation:** Cubic spline to fill missing annual values (1996–2024).  
- **Models tested:** Linear (deg 1), quadratic (deg 2), cubic (deg 3) polynomials:  
  \[ y_t = α + β₁t + β₂t² + β₃t³ + ε_t \]  
- **Model selection:** lowest AIC for each indicator.  
- **Forecast horizon:** 2025–2030.  
- **Evaluation metrics:** RMSE, MAE, MAPE/sMAPE, Theil’s U (bias/variance decomposition) :contentReference[oaicite:2]{index=2}.

---

## 📈 Results & Discussion

1. **Model fits & AIC**  
   - Cubic best for P0 and Gini; quadratic suffices for P1; cubic again for P2 (see Table 0.2).  
2. **Forecast trajectories**  
   - All poverty measures (P0–P2) decline through 2030; Gini drops toward ~0.32 by 2030.  
   - Confidence bands widen with horizon, reflecting uncertainty :contentReference[oaicite:3]{index=3}.  
3. **Performance**  
   - Low RMSE/MAE and MAPE < 10%; Theil’s U ≪ 1 indicates minimal bias and good variance reproduction.  

---

## 🔮 Conclusion & Perspectives

- **Key findings:** Significant long-term decline in poverty and inequality under stable macro assumptions.  
- **Methodological note:** Polynomial trends capture inflections and curvature better than linear.  
- **Future work:**  
  - Integrate economic covariates (sectoral growth, unemployment, social transfers)  
  - Test ARIMA/SARIMA or ML methods, and scenario-based (commodity shocks, climate events) forecasts.  

---

## 🛠️ How to Run

1. Clone this repo:  
   ```bash
   git clone https://github.com/<your-org>/poverty-gini-forecast.git
   cd poverty-gini-forecast
## 📂 Repository Structure

```text
Prévision/
├── data/
│   ├── indicateurs_Pauvrete.xlsx       # Raw P0, P1, P2 & Gini data (1996–2024)
│   └── donnees_interpolees.xlsx        # Spline‐interpolated annual series
├── notebooks/
│   └── Projet_Prévision.Rmd            # Data preparation & interpolation and Model fitting & forecasting
└── README.md                           # ← You are here
