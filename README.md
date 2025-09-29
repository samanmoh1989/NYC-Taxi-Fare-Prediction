# NYC Yellow Taxi Fare Prediction (2019)

## Introduction
The New York City Taxi and Limousine Commission (NYC TLC) collects detailed trip records for all yellow taxi rides in the city. 
This project explores taxi trip data and builds a **multiple linear regression model** to predict taxi fares using trip-related features.

The workflow demonstrates a full data science pipeline:
- **Data exploration (EDA):** Understanding distributions, correlations, and detecting outliers.
- **Data cleaning & preprocessing:** Handling missing values, capping outliers (e.g., fares capped at $65.50), and engineering features such as trip duration, mean distance, and rush-hour indicators.
- **Feature engineering:** Creating new predictors such as `duration`, `mean_distance`, `mean_duration`, and rush-hour flags.
- **Modeling:** Building and evaluating a regression model to predict `fare_amount`.
- **Evaluation:** Assessing performance with R², MAE, MSE, and RMSE, plus residual diagnostics.

---

## Dataset
- Source: [NYC Open Data – TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- Sampled ~500,000 rides for analysis and modeling.
- Features include pickup/dropoff timestamps, trip distance, passenger count, and fare components.

---

## Results
- **R² ≈ 0.86** → 86% of variance in fare amounts explained by the model.
- **MAE ≈ 1.6** → On average, fares predicted within ~$2 of the true value.
- **RMSE ≈ 4.3** → Relatively small errors compared to the full fare range.
- Residuals are approximately normally distributed around zero, indicating the model is unbiased.

---

## Conclusion
This project demonstrated an end-to-end workflow for predicting NYC yellow taxi fares.  

Key findings include:
- **Trip distance** and **trip duration** are the strongest predictors of fare amount.  
- The multiple linear regression model explained about **86% of the variance** in fares.  
- The average prediction error was **less than $2 (MAE)**, which is acceptable given the variability of taxi fares.  
- Residual analysis showed that the model is generally unbiased, though it tends to slightly underpredict very high fares and overpredict very low fares.  

Future improvements could include testing non-linear models (e.g., Random Forest, Gradient Boosting) and incorporating additional external data such as weather or traffic conditions.

---

## Repository Structure
```
NYC-Taxi-Fare-Prediction/
├── data/               # optional: sample dataset(s)
├── notebooks/          # Jupyter notebooks (main analysis here)
├── reports/            # key plots/figures
├── requirements.txt    # dependencies
└── README.md           # project description
```

---

## How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/NYC-Taxi-Fare-Prediction.git
   cd NYC-Taxi-Fare-Prediction
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook and open the analysis:
   ```bash
   jupyter notebook notebooks/NYC_Yellow_Taxi_Trip_Data_Analysis.ipynb
   ```

---

## Requirements
See `requirements.txt` for Python dependencies.

---

## License
This project is released under the MIT License. Data is sourced from NYC TLC Open Data and subject to their terms of use.
