# Life Expectancy Prediction

Predicting life expectancy using machine learning on WHO data from 193 countries (2000-2015).

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## Overview

This project analyzes health, economic, and social factors that affect life expectancy across different countries. Using data from the World Health Organization, I built machine learning models to predict life expectancy and identify the most important contributing factors.

**Best Model Performance:** Extra Trees Regressor with 97.4% R² score

## Dataset

- **Source:** WHO Global Health Observatory
- **Records:** 2,938
- **Countries:** 193
- **Time Period:** 2000-2015
- **Features:** 22 health, economic, and social indicators

### Features Used

| Category | Features |
|----------|----------|
| Health | Life Expectancy, Adult Mortality, Infant Deaths, HIV/AIDS, BMI |
| Immunization | Hepatitis B, Polio, Diphtheria |
| Economic | GDP, Healthcare Expenditure, Income Composition |
| Social | Schooling, Population, Development Status |

## Results

### Model Comparison

| Model | R² Score | RMSE (years) |
|-------|----------|--------------|
| Extra Trees | 0.9739 | 1.50 |
| Random Forest | 0.9658 | 1.72 |
| Gradient Boosting | 0.9446 | 2.19 |
| Ridge | 0.8533 | 3.56 |
| Linear Regression | 0.8533 | 3.57 |

### Key Findings

1. **HIV/AIDS** is the strongest predictor of life expectancy (56% feature importance)
2. **Education** (schooling years) shows strong positive correlation (r = 0.75)
3. **Development gap:** Developed countries have ~12 years higher life expectancy
4. **Improving trend:** Global life expectancy increased by 4 years between 2000-2015

### Top Predictors

| Feature | Correlation |
|---------|-------------|
| Schooling | +0.75 |
| Income Composition | +0.72 |
| BMI | +0.57 |
| Adult Mortality | -0.70 |
| HIV/AIDS | -0.56 |

## Project Structure

```
├── data/
│   └── Life_Expectancy_Data.csv
├── cleaned_data/
│   ├── life_expectancy_cleaned.csv
│   ├── model_results.csv
│   └── feature_importance.csv
├── visualizations/
│   ├── 01_distribution.png
│   ├── 02_boxplot_status.png
│   ├── 03_yearly_trend.png
│   ├── 04_trend_by_status.png
│   ├── 05_correlation_heatmap.png
│   ├── 06_feature_correlations.png
│   ├── 07_scatter_plots.png
│   ├── 08_outliers.png
│   ├── 09_model_comparison.png
│   ├── 10_feature_importance.png
│   ├── 11_predictions.png
│   └── 12_cross_validation.png
├── life_expectancy_analysis.ipynb
├── analysis.py
├── dashboard.html
├── README.md
└── requirements.txt
```

## Installation

```bash
git clone https://github.com/yourusername/life-expectancy-prediction.git
cd life-expectancy-prediction
pip install -r requirements.txt
```

## Usage

**Option 1: Jupyter Notebook**
```bash
jupyter notebook life_expectancy_analysis.ipynb
```

**Option 2: Python Script**
```bash
python analysis.py
```

**Option 3: View Dashboard**
Open `dashboard.html` in your browser

## Visualizations

### Life Expectancy Distribution
![Distribution](visualizations/01_distribution.png)

### Developed vs Developing Countries
![Trend](visualizations/04_trend_by_status.png)

### Correlation Heatmap
![Correlation](visualizations/05_correlation_heatmap.png)

### Model Performance
![Models](visualizations/09_model_comparison.png)

### Feature Importance
![Features](visualizations/10_feature_importance.png)

## Methodology

1. **Data Cleaning**
   - Imputed missing values using mean
   - Handled outliers using IQR method
   - Encoded categorical variables

2. **Feature Engineering**
   - Created Mortality Ratio
   - Created Immunization Score
   - Created GDP-Income composite

3. **Model Training**
   - Trained 5 different regression models
   - Used 80-20 train-test split
   - Performed 10-fold cross-validation

4. **Evaluation**
   - Compared models using R², RMSE, MAE
   - Analyzed feature importance
   - Conducted statistical tests

## Tech Stack

- Python 3.8+
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- scipy

## License

MIT

## Author

[Your Name](https://github.com/yourusername)
