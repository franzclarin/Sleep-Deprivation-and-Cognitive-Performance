# Sleep Deprivation and Cognitive Performance

An R/Quarto analysis of how sleep deprivation and lifestyle factors affect cognitive performance.

## Goals

- Understand the effects of sleep deprivation (sleep hours, sleep quality, daytime sleepiness) and behavioral health factors (BMI, caffeine intake, physical activity, stress) on cognitive performance (attention, working memory, reaction speed, emotion regulation).
- Model each cognitive performance outcome using sleep and behavioral health predictors.

## Data

`sleep_deprivation_dataset_detailed.csv` — n = 60 participants with the following variables:

| Category | Variables |
|---|---|
| Sleep | `Sleep_Hours`, `Sleep_Quality_Score`, `Daytime_Sleepiness` |
| Cognitive outcomes | `Stroop_Task_Reaction_Time`, `N_Back_Accuracy`, `PVT_Reaction_Time`, `Emotion_Regulation_Score` |
| Lifestyle | `Age`, `BMI`, `Gender`, `Caffeine_Intake`, `Physical_Activity_Level`, `Stress_Level` |

## Analysis

All analysis is in `analysis.qmd` (render with Quarto to produce `analysis.html`).

### Structure

1. **EDA**
   - Univariate distributions for all variable groups
   - Correlation matrix across all numeric variables
   - Scatterplots: sleep hours and sleep quality vs. each cognitive outcome
   - K-Means clustering: behavioral profiles and sleep/cognitive profiles

2. **Models** (repeated for each of the 4 cognitive outcomes)
   - Model 1: Unadjusted OLS (sleep variables only)
   - Model 2: Adjusted OLS (sleep + lifestyle covariates)
   - Model 3: LASSO with 10-fold cross-validation
   - Coefficient plots and residual diagnostics

### Key Visualizations

| # | Plot | Purpose |
|---|---|---|
| 1 | Correlation matrix | Overview of all pairwise relationships |
| 2 | Sleep Hours vs. Cognitive Outcomes scatterplots | Primary research question |
| 3 | Cognitive performance distributions | Context for outcome variables |
| 4 | K-Means: Sleep & Cognitive Profiles (PCA + boxplots) | Natural subgroups in the data |
| 5 | OLS coefficient plots (unadjusted vs. adjusted) | Model results across all 4 outcomes |

## Requirements

```r
install.packages(c(
  "readr", "ggplot2", "tidyverse", "patchwork",
  "cluster", "factoextra", "glmnet", "broom"
))
```
