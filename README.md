# Seattle Weather Prediction — Data Analytics Project

A complete end-to-end machine learning project that analyses historical Seattle weather data (2012–2015) and builds predictive models to classify daily weather conditions.

---

## Project Structure

```
├── seattle-weather.csv          # Raw dataset (1461 daily records)
├── weather_analysis.ipynb       # Main Jupyter notebook (all analysis + models)
├── requirements.txt             # Python dependencies
├── README.md                    # This file
└── weather_report.docx          # Full project report with charts
```

---

## Dataset

| Column          | Description                        |
|-----------------|------------------------------------|
| `date`          | Date of observation (YYYY-MM-DD)   |
| `precipitation` | Precipitation in mm                |
| `temp_max`      | Maximum temperature (°C)           |
| `temp_min`      | Minimum temperature (°C)           |
| `wind`          | Wind speed (m/s)                   |
| `weather`       | Target label: sun, rain, drizzle, snow, fog |

- **Records:** 1,461 daily observations (Jan 2012 – Dec 2015)
- **Source:** Kaggle Seattle Weather dataset [https://www.kaggle.com/datasets/ananthr1/weather-prediction]

---

## Analysis Sections

1. **Exploratory Data Analysis (EDA)**
   - Distribution of weather classes
     <img width="1536" height="1212" alt="plot_feature_distributions" src="https://github.com/user-attachments/assets/7e387b95-4762-40e7-afb7-12b3926c3c09" />

   - Seasonal temperature trends
     <img width="1296" height="576" alt="plot_monthly_temperature" src="https://github.com/user-attachments/assets/d802f64f-78c0-4993-b477-096e574d4d49" />

   - Precipitation patterns by month
     <img width="1296" height="576" alt="plot_monthly_precipitation" src="https://github.com/user-attachments/assets/4f14028a-5d76-4bb9-bb29-cdadeca2b984" />

   - Correlation heatmap of numeric features
     <img width="665" height="576" alt="plot_correlation_heatmap" src="https://github.com/user-attachments/assets/cd3a7785-9bf9-412e-8226-4c2dfd7ec5d4" />


2. **Feature Engineering**
   - Temporal features: month, season, day-of-year
   - Derived features: temp_range (max − min)
   - Label encoding of target variable

3. **Predictive Modelling**
   - Logistic Regression (baseline)
   - Random Forest Classifier
   - XGBoost Classifier
   - 80/20 train-test split, stratified

4. **Model Evaluation**
   - Accuracy, Precision, Recall, F1-score
   - Confusion matrices
   - Feature importance plots
   - ROC-AUC (one-vs-rest)

5. **Results Summary**
   - Best model comparison table
     <img width="1056" height="576" alt="plot_model_comparison" src="https://github.com/user-attachments/assets/5ca36ff4-ea6d-45d6-a4ae-5d0d1d02091e" />

   - Key insights from the data
     -Temperature is the most discriminative feature: temp_max and temp_min together account for over 50% of the           Random Forest predictive power.
     -	Seasonality provides significant signal: engineered month and day_of_year features ranked 5th and 6th in             importance, validating the feature engineering step.
     -	Class imbalance impacts rare classes: fog and snow have very few test samples (< 15 each), making precision/recall for these classes unreliable. SMOTE oversampling could improve this.
     -	Ensemble methods dominate: Random Forest outperforms Logistic Regression by ~7.8 percentage points, consistent across all CV folds.
     -	Precipitation separates rain from drizzle: precipitation > 5mm strongly predicts rain, while 0-2mm with cool temperatures indicates drizzle.
     -	Wind speed is the weakest predictor: contributing only ~7% of feature importance; it could be dropped with minimal accuracy loss.


---

## Setup & Running

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

### 2. Launch Jupyter

```bash
jupyter notebook weather_analysis.ipynb
```

### 3. Run all cells

Use **Kernel → Restart & Run All** to execute the full notebook from top to bottom.

---

## Requirements

- Python 3.9+
- See `requirements.txt` for full package list

---

## Key Results (Summary)

| Model               | Accuracy |
|---------------------|----------|
| Logistic Regression | ~79%     |
| Random Forest       | ~85%     |
| XGBoost             | ~86%     |

*Actual values printed in the notebook after execution.*

---

## Technologies Used
- Python
- Pandas
- Numpy
- Seaborn
- Scikit-learn
- Matplotlib

---

## License

This project is for educational and analytical purposes. Dataset sourced from Kaggle.
