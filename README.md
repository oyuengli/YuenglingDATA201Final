# DATA 201 Final Project: CIA World Factbook Analysis

**Author:** Olivia Yuengling  
**Date:** December 16, 2024

## Project Overview
This project analyzes the **CIA 2014 World Factbook** dataset to investigate global demographic patterns. The research is divided into two major components:
1.  **Regression Modeling:** Predicting the **Net Migration Rate** based on birth rates, death rates, and population growth.
2.  **Classification Modeling:** Determining if a country qualifies as **"Third World" (underdeveloped)** based on 2014 United Nations criteria.

## Data Source
The dataset is sourced from the CIA World Factbook, accessed via [TidyTuesday (Week 43, 2024)](https://github.com/rfordatascience/tidytuesday/blob/main/data/2024/2024-10-22/readme.md). It includes intelligence on 265 world entities, focusing on population-based metrics such as area, internet usage, mortality rates, and vital statistics.

## Repository Structure
* `Yuengling_DATA201_AppendixA_F24.Rmd`: Analysis of migration rates using Linear and Polynomial Regression.
* `Yuengling_DATA201_AppendixB_F24.Rmd`: Classification of country status using Logistic Regression, Random Forest, and ANN.
* `Yuengling_DATA201_FinalProject.pdf`: The final summary report of the research findings.

## Methodology

### Data Cleaning & Processing
* **Imputation:** Missing values were handled using mean imputation for normally distributed data (e.g., population growth) and median imputation for skewed data (e.g., infant mortality).
* **Feature Engineering:** Created a binary `third_world` variable by cross-referencing the UN "Least Developed Countries" report.
* **Geopolitical Context:** Identified and analyzed extreme outliers in migration rates for Syria and Lebanon, corresponding to the impact of the Syrian Civil War (2011–2014).

### Modeling & Performance

#### 1. Regression (Predicting Net Migration)
We compared a standard Linear Model against a Polynomial Model to see which better captured demographic shifts.
* **Key Predictors:** Birth rate, death rate, and population growth rate.
* **Results:** The **Polynomial Model** was superior, achieving an **RMSE of 0.56** compared to the Linear Model's 1.34.

#### 2. Classification (Third World Status)
We evaluated three algorithms to classify countries as "Developed" vs. "Third World."
* **Logistic Regression:** Achieved 93.02% accuracy with excellent sensitivity (97.06%).
* **Random Forest:** Achieved 88.36% accuracy and was determined to be the **most reliable** model due to its consistency across cross-validation folds.
* **Artificial Neural Network (ANN):** Achieved 89.02% accuracy but showed some performance inconsistencies.



## Key Findings
* **Migration Drivers:** Net migration is heavily influenced by the balance of birth and death rates, though non-linear polynomial modeling is required to achieve high accuracy.
* **Development Indicators:** Basic vital statistics (death rates and growth rates) are highly proficient at predicting a country's development status.
* **Model Selection:** While Logistic Regression had the highest top-level accuracy, **Random Forest** proved more robust for generalized classification in this dataset.

## How to Run
1. Clone the repository.
2. Ensure you have R installed along with the following libraries: `tidyverse`, `caret`, `ISLR2`, `GGally`, `mlbench`, and `car`.
3. Open the `.Rmd` files in RStudio and knit to PDF or HTML to reproduce the full analysis.
