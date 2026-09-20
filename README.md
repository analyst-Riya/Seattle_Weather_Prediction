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
   - Seasonal temperature trends
   - Precipitation patterns by month
   - Correlation heatmap of numeric features

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
   - Key insights from the data

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

## License

This project is for educational and analytical purposes. Dataset sourced from Kaggle.
