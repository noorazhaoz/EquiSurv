# EquiSurv
# Fairness-Aware Processing Techniques in Survival Analysis: Promoting Equitable Predictions

## Introduction
This project adapts and extends several pre-processing and post-processing approaches from classification and regression contexts to survival analysis. The proposed techniques are model-agnostic, flexible, intuitive, and explainable. The goal of this project is to improve fairness in predictive models.

## Methods and Experimental Studies
We conduct experimental studies using both medical and non-medical datasets to assess whether and to what extent the proposed methods improve fairness. Our work considers the trade-offs among proposed methods in terms of group fairness, individual fairness, and predictive performance.

## Data 
The datasets used for this project fall into two categories: medical and non-medical data. 

### Medical Data:

| Dataset | Source |
|---------|--------|
| FLCHAIN | [scikit-survival Python package](https://github.com/sebp/scikit-survival) |
| NAFLD1  | [survival package in R](https://cran.r-project.org/web/packages/survival/index.html) |
| Tumor   | [pammtools package in R](https://cran.r-project.org/web/packages/pammtools/index.html) |
| WHAS500 | [scikit-survival Python package](https://github.com/sebp/scikit-survival) |

### Non-Medical Data:

|         Dataset        |          Source        |
|------------------------|------------------------|
| Employee Turnover      | [Kaggle Dataset](https://www.kaggle.com/datasets/davinwijaya/employee-turnover) |
| Customer Subscription  | [Kaggle Dataset](https://www.kaggle.com/datasets/gsagar12/dspp1) |


## Methods

Our approach includes both pre-processing and post-processing methods:

### Pre-processing methods
1. **Disparate Impact Remover:** Adjusts the distribution of ordinal non-sensitive features while preserving original ranks.
2. **Data Augmentation with Identical Copies:** Creates identical copies of each training instance for all sensitive attribute values.
3. **Correlation Remover:** This method aims to eliminate the linear dependence between non-sensitive and sensitive attributes, while keeping as much detail as possible from the original data. 

4. **Sampling:** Divides the data set based on the sensitive attribute and class label, and samples each group separately until the expected group size is reached.

### Post-processing methods
1. **Post-processing by controlling for sensitive attributes:** Involves fitting a model with both sensitive and non-sensitive attributes as predictors. The fitted model is then averaged across the values of sensitive attributes in the population.
