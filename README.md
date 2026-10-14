# Parkinson's Disease Voice Biomarkers

## Research Question
To what extent do traditional and nonlinear acoustic voice biomarkers predict Parkinson's disease severity, as measured by the Unified Parkinson's Disease Rating Scale (UPDRS), and does combining these feature types improve predictive performance?

Addtionally, do nonlinear voice features provide additional predictive information beyond traditional acoustic features?

## Overview
By using data collected from a publically available dataset, we analyzed the traditional and nonlinear features to determine it is succesful in predicting Total UPDRS for Parkinson's Disease severity. The frame using three models across 23 metrics. Metrics evaluated include Jitter, Shimmer, RPDE, DFA, PPE, HNR, and NHR. Models used include Random Forest, Gradient Booster, and Linear Regression.

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

This project emphasizes evaluation not based on model training
