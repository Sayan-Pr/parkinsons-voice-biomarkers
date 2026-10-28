# Parkinson's Disease Voice Biomarkers

## Research Question
To what extent do traditional and nonlinear acoustic voice biomarkers predict Parkinson's disease severity, as measured by the Unified Parkinson's Disease Rating Scale (UPDRS), and does combining these feature types improve predictive performance?

Addtionally, do nonlinear voice features provide additional predictive information beyond traditional acoustic features?

## Overview
This project investigates whether traditional acoustic and nonlinear voice biomarkers can predict Parkinson's disease severity, measured by the Total Unified Parkinson's Disease Rating Scale (Total UPDRS). Using a publicly available Parkinson's telemonitoring dataset, the analysis compares traditional acoustic features, nonlinear voice features, demographic variables, and selected combinations of these features.

Three regression models (Linear Regression, Random Forest Regression, and Gradient Boosting Regression) are evaluated to examine predictive performance and determine whether combining traditional and nonlinear features provides additional predictive information. The project emphasizes patient-level generalization rather than performance on recordings from individuals represented during training.

## Dataset Information
Name: Parkinson's Telemonitoring Data
Source: UCI Machine Learning Repository (acquired via Kaggle)
Rows: 5875
Columns: 22

Because multiple recordings come from the same individual, recordings are not statistically independent. Patient-level separation is therefore important when evaluating generalization to new individuals.

Target:
total_UPDRS
Mean = 29.018942
Range = 7 - 54.992

Feature categories:
Traditional acoustic features 
- Jitter
- Shimmer
- Noise-to-harmonics ratio (NHR)
- Harmonics-to-noise ratio (HNR)

Nonlinear voice features
- Recurrence period density entropy (RPDE)
- Detrended fluctuation analysis (DFA)
- Pitch period entropy (PPE)

Demographic features
- Age
- Sex

The combined features are selected number of acoustic and nonlinear combinations

Missing values:
None

Sex:
Female - 4008
Male - 1867

Age:
Mean = 64.084936 years
Range = 36-85 years

## Methodology
Models Used
- Linear Regression
- Random Forest Regression (RF)
- Gradient Boostin Regression (GB)

Feature Configurations
Models are evaluated using the feature combinations that were used in the analysis, including traditional acoustic features, nonlinear voice features, demographic variables, and selected combinations.

Validation Strategy
Because the dataset contains repeated recordings from individual participants, random splitting by recording could allow recordings from the same participant to appear in both training and testing sets. This can overestimate generalization performance.

To address this issue, the analysis uses participant-grouped data splitting and cross-validation, keeping recordings from the same participant within a single group.

Evaluation Metrics
Model performance is assessed using:
- R²: Measures predictive fit relative to a mean-based baseline. Negative values indicate performance worse than that baseline on the evaluated data.
- Mean Absolute Error (MAE): Measures the average absolute difference between predicted and observed Total UPDRS values.
- Root Mean Squared Error (RMSE): Measures prediction error while penalizing larger errors more heavily.

Research Focus
The study examines whether nonlinear features can provide additional predictive information beyond what traditional acoustic features offer and whether combining feature categories improves performance on unseen participants.

## Results

Model Performance
| Feature Configuration | Model | R² | MAE | RMSE |
|---|---|---:|---:|---:|
| Traditional Acoustic | Linear Regression | −0.262 ± 0.314 | 9.244 ± 1.789 | 11.136 ± 1.777 |
| Traditional Acoustic | Random Forest | −0.323 ± 0.285 | 9.383 ± 1.601 | 11.404 ± 1.568 |
| Traditional Acoustic | Gradient Boosting | −0.325 ± 0.314 | 9.425 ± 1.597 | 11.392 ± 1.555 |
| Nonlinear Voice | Linear Regression | −0.208 ± 0.313 | 9.058 ± 1.711 | 10.919 ± 2.043 |
| Nonlinear Voice | Random Forest | −0.348 ± 0.427 | 9.292 ± 1.305 | 11.439 ± 1.798 |
| Nonlinear Voice | Gradient Boosting | −0.317 ± 0.383 | 9.240 ± 1.331 | 11.334 ± 1.797 |
| Combined Features | Linear Regression | −0.258 ± 0.298 | 9.294 ± 1.661 | 11.164 ± 2.087 |
| Combined Features | Random Forest | −0.353 ± 0.357 | 9.485 ± 1.501 | 11.521 ± 1.844 |
| Combined Features | Gradient Boosting | −0.344 ± 0.349 | 9.426 ± 1.373 | 11.475 ± 1.721 


Feature Comparison
The performance of the feature combinations was compared to assess whether nonlinear voice features provided additional predictive information beyond traditional acoustic features. The combined-feature models were evaluated against corresponding traditional-feature and nonlinear-feature models using the same patient-level validation strategy. Differences in R², MAE, and RMSE were examined to determine whether combining feature categories improved predictive performance.

Key Findings
The best performing feature-model combination was clinical features under Linear Regression. However, between either nonlinear or traditional features, the best feature-model combination was traditional features through Linear Regression. Each model was evaluated using patient-level validation to assess their ability to generalize to previously unseen participants. The study emphasizes the distinction between predicting recordings from familiar participants and generalizing to new individuals. Negative R² values indicate that the evaluated models performed worse than a mean-based prediction baseline on the corresponding evaluation data.

## Reproducibility
The analysis uses Python and the following libraries:
- NumPy
- pandas
- scikit-learn
- Matplotlib
- Seaborn
- SciPy

Dataset Access
- This project uses the Parkinson's Telemonitoring dataset, originally available through the UCI Machine Learning Repository and accessed via Kaggle.
- The dataset contains 5,875 voice recordings from 42 individuals. The target variable is `total_UPDRS`.
- The dataset is not included in this repository. Obtain it from the original source or the source used in this analysis, and review its applicable terms of use before redistributing it.

Installation
Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/parkinsons-voice-biomarkers.git
cd parkinsons-voice-biomarkers
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Running the Analysis
1. Open `notebooks/Parkinsons_Voice_Biomarkers.ipynb`.
2. Obtain the dataset and make it available to the notebook.
3. Update the dataset file path if necessary.
4. Install the required dependencies.
5. Run the notebook cells in order, from top to bottom.

The analysis includes data exploration, feature evaluation, regression modeling, and patient-level validation.

Reproducibility Notes
Results may vary depending on package versions, random seeds, data preprocessing, and validation settings. Refer to the notebook for the implemented methodology and evaluation procedures.


