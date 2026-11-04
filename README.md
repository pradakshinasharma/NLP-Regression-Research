
# NLP and Regression Research: Real Estate Price Prediction

This project explores real-estate listing price prediction using structured property features and natural language processing. It investigates whether incorporating listing descriptions improves regression performance.

## Project Overview

The target variable is `listPrice`. The experiments compare regression models trained on:

- **Structured features:** Property characteristics such as square footage, number of bedrooms and bathrooms, stories, garage, year built, and property-type indicators.
- **Text features:** Listing descriptions transformed into numerical representations using TF-IDF.
- **Combined features:** Structured and text features joined using SciPy's sparse matrix functionality.

The data was divided into training, validation, and test sets (70% / 15% / 15%).

## Models and Experiments

The repository contains the following notebooks:

| Notebook | Description |
|---|---|
| `RF_NOTEXT.ipynb` | Random Forest using structured features |
| `RF_TEXT (1).ipynb` | Random Forest incorporating listing text |
| `ridgeregression_notext.ipynb` | Ridge Regression using structured features |
| `ridgeregression_text.ipynb` | Ridge Regression incorporating listing text |
| `XGBoost.ipynb` | XGBoost regression experiments |

The experiments include hyperparameter tuning and comparisons between models with and without text features.

## Results

The following test-set results were recorded in the notebooks:

| Model | Features | R² | RMSE | MAE |
|---|---|---:|---:|---:|
| Random Forest | Structured | 0.5574 | 0.4304 | 0.2822 |
| Random Forest | Structured + Text | 0.6151 | 0.4013 | 0.2474 |
| Ridge Regression | Structured | 0.4507 | 0.4663 | 0.3050 |
| Ridge Regression | Structured + Text | 0.6668 | 0.3734 | 0.2368 |

These results suggest that incorporating listing descriptions improved performance in the recorded Random Forest and Ridge Regression experiments.

*Note: These are results from separate notebook experiments, not a fully controlled benchmark. Metrics are reported on the target scale used in the notebooks.*

## Repository Structure

```text
NLP-Regression-Research/
├── RF_NOTEXT.ipynb
├── RF_TEXT (1).ipynb
├── ridgeregression_notext.ipynb
├── ridgeregression_text.ipynb
├── XGBoost.ipynb
├── cleaned_without.csv
└── cleaned_with_text.csv
```

## Technologies

- Python
- pandas and NumPy
- scikit-learn
- SciPy
- TF-IDF Vectorization
- Random Forest Regression
- Ridge Regression
- XGBoost
- Optuna
- Matplotlib
- joblib

## Running the Project

1. Clone the repository.
2. Install the required Python libraries used in the notebooks.
3. Open the notebooks using Jupyter Notebook or JupyterLab.
4. Run the experiments to explore preprocessing, feature engineering, model training, and evaluation.

The notebooks contain the individual experiment workflows and results.
