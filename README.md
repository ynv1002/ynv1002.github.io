# 🏠 Short-Term Rentals & Crime Analysis in New Orleans

**Team Members:** Yaniv Naggar & Nick Chvany  
**GitHub Pages Website:** [ynv1002.github.io](https://ynv1002.github.io)

---

## 📌 Project Overview

This project explores the relationship between short-term rental (STR) density and crime rates in New Orleans. With the city’s evolving STR regulations and growing concerns over housing and safety, our goal is to analyze whether areas with more STRs are associated with increased incidents of crime.

---

## ❓ Research Questions

- Do high-density STR areas experience more crime?
- Are STR applications more likely to be denied in high-crime areas?
- Can we build a model to predict high-crime zones based on STR features?

---

## 🗂️ Data Sources

- **Short-Term Rental License Applications**  
  [Data Source](https://data.nola.gov/) — Permit status, type, and owner/zoning details.

- **New Orleans Police Incident Reports (2025)**  
  [Data Source](https://data.nola.gov/) — Incident location, crime type, and timestamps.

---

## 🔍 Key Findings

- **High Denial Rate:** 23.94% of STR applications were denied.
- **Large Backlog:** 9.57% of STR applications remain pending.
- **Revocations:** 144 permits were revoked, suggesting enforcement of violations.
- **Density & Crime Correlation:**  
  Commercial STRs showed the strongest positive correlation (r = 0.82) with property crime density.

---

## 🧪 Methodology

1. **Data Cleaning & Tidy Restructuring**
   - Standardized text fields and removed bad coordinates.
   - Filtered and created subsets: Active, Commercial, and Non-Commercial STRs.

2. **Geospatial Aggregation**
   - Rounded coordinates to 2 and 3 decimal precisions.
   - Created `coord_key` for spatial merging of STR and crime datasets.

3. **Visual Analysis**
   - Used Folium maps and Seaborn scatterplots to examine STR clustering and crime trends.
   - Stratified by STR type to isolate commercial effects.

4. **Normalization**
   - Applied MinMaxScaler to align units for modeling.

5. **Modeling**
   - **Model Type:** K-Nearest Neighbors (KNN)
   - **Target:** Predict whether an STR is in a high-crime area (above 75th percentile).
   - **Features:** STR density + commercial status
   - **Performance:**  
     - Accuracy: 97%  
     - F1 Score (High Crime): 0.93  
     - Confusion Matrix showed strong performance across both classes.

---

## 📈 Next Steps

- Investigate temporal policy shifts and their impact on STR clustering.
- Extend to predicting STR denials using zoning, crime, and density features.
- Explore socioeconomic overlays (e.g., income, vacancy rates) for fairness analysis.

---

## 📚 References

- New Orleans City Planning Commission. (2018). *Affordable Housing & STRs*.
- WWNO (2025). *New STR Ordinance Summary*.
- PMC (2021). *Short-Term Rentals and Crime: Boston Case Study*.
