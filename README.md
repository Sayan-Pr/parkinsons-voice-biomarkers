# Parkinson's Disease Voice Biomarkers

## Research Question
To what extent do traditional and nonlinear acoustic voice biomarkers predict Parkinson's disease severity, as measured by the Unified Parkinson's Disease Rating Scale (UPDRS), and does combining these feature types improve predictive performance?

## Overview
By using data collected from a publically available dataset, we analyzed the traditional and nonlinear features to determine it is succesful in detecting early symptoms of Parkinson's Disease. The frame using three models across 23 metrics. Metrics evaluated include Jitter, Shimmer, RPDE, DFA, PPE, HNR, and NHR. Models used include Random Forest, Gradient Booster, and Linear Regression.

## Dataset Information
Name: Parkinson's Telemonitoring Data
Source: UCI Machine Learning Repository (acquired via Kaggle)
Rows: 5875
Columns: 22

Target:
total_UPDRS
Mean = 29.018942
Range = 7 - 54.992

Feature categories:
Demographic
Clinical
Acoustic
Traditional
Nonlinear
Target

Missing values:
None

Sex:
Female - 4008
Male - 1867

Age:
Mean = 64.084936 years
Range = 36-85 years


## Methodology

