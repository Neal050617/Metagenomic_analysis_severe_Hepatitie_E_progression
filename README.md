# Clinical severity score guided metagenomic analysis identifying gut microbial taxonomic and functional markers for severe hepatitis E progression

This repository contains four R-based analysis scripts for a metagenomic study focused on severe hepatitis E progression. The workflow integrates clinical severity scoring with gut microbial taxonomic and functional analyses to identify biomarkers associated with disease severity.

## Project overview

This study aims to:
- construct a clinically informed severity score;
- evaluate the predictive value of microbial features using machine learning models;
- identify taxonomic markers associated with disease status and severity;
- analyze functional gene profiles and pathway-level associations after confounder adjustment.

## Repository contents

1. Task 1: adjusted clinical final score calculation
   - Constructs a clinical severity scoring framework.
   - Includes trend-based testing, FDR correction, exhaustive candidate search, and composite score generation.
   - Incorporates confounder adjustment for age, sex/gender, and BMI where available.

2. Task 2: XGBoost classification analysis (HC vs patient)
   - Performs binary classification between healthy controls and patients.
   - Uses XGBoost with confounder-aware modeling.
   - Evaluates model performance using bootstrap resampling and classification metrics.

3. Task 3: XGBoost regression with bootstrap, 5-fold cross-validation, and permutation analysis
   - Builds regression models for continuous clinical severity outcomes.
   - Applies bootstrap validation, 5-fold cross-validation, and permutation testing.
   - Estimates feature importance and derives a composite ranking of microbial contributors.

4. Task 4: microbial gene analysis with confounder adjustment
   - Analyzes KO-level functional gene features.
   - Applies CLR transformation, confounder adjustment, feature selection, and pathway mapping.
   - Performs enrichment analysis at the pathway level.

## Expected input data

The scripts assume that relevant input files are available in the working directory or are modified to match the local file paths. In particular, the analyses may require files such as:
- Supplementary table S1.xlsx
- haiyan_species (1).xlsx
- sample functional gene data files
- KO-to-pathway mapping files

Please update the file paths in the scripts if your data is stored in a different directory.

## Software requirements

These scripts are written in R and require the following major packages:
- MASS
- dplyr
- tidyr
- ggplot2
- xgboost
- caret
- pROC
- openxlsx
- readxl
- glmnet
- VennDiagram
- UpSetR
- patchwork
- ggrepel
- RColorBrewer
- viridis
- ggdist
- broom
- psych

## Notes

- Some scripts contain comments in Chinese and English mixed with code annotations.
- The repository currently includes analysis scripts rather than processed results or raw data files.
- The analysis workflow is intended for research and exploratory data analysis rather than direct clinical decision-making.
