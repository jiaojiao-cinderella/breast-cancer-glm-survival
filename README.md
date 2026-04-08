# GLM for Breast Cancer Prediction

## Project Overview
This project applies Generalized Linear Models (GLM) to analyze how genomic instability markers predict overall survival in breast cancer patients.

The study evaluates mutation count, fraction genome altered (FGA), microsatellite instability (MSI), and clinical factors such as metastatic status and cancer type.

## Research Question
How do genomic instability markers predict overall survival in breast cancer patients?

## Dataset
Source: MSK-IMPACT Breast Cancer dataset from cBioPortal  
Samples: 3,879 tumor samples  
Patients: 3,117 unique patients  
Variables: 25 clinical and genomic variables  

## Methods

### Data Preprocessing
Missing values below 3 percent were removed using listwise deletion.  
Mutation count was log transformed.  
MSI score was converted into a categorical variable.  
Binary variables were created for survival status and metastatic status.  

### Exploratory Data Analysis
Data distributions and skewness were examined.  
Correlation analysis showed no multicollinearity issues.  
Group comparisons indicated that higher mutation count and higher FGA are associated with increased mortality.  
Metastatic tumors showed substantially higher mortality rates.  

### Model Building
Three logistic regression models were evaluated:

Model 1: Main effects only  
Model 2: Mutation Count multiplied by Metastatic Status  
Model 3: Fraction Genome Altered multiplied by Metastatic Status  

Model 3 was selected as the final model based on AIC and goodness-of-fit testing.

## Results
Metastatic status is the strongest predictor of mortality.  
Fraction Genome Altered is the most important genomic predictor.  
A significant interaction exists between FGA and metastatic status.  

FGA strongly predicts mortality in primary tumors but has a weaker effect in metastatic tumors.

Model performance:
AUC approximately 0.74  
Model shows good calibration  

## Model Specification
The final logistic regression model is:

log(p / (1 - p)) =
beta0 + beta1(Log Mutation Count) + beta2(FGA) + beta3(Metastatic) +
beta4(MSI Type) + beta5(Cancer Type) + beta6(Tumor Purity) +
beta7(FGA multiplied by Metastatic)

## Visualizations
The project includes distribution plots, correlation analysis, boxplots, interaction plots, ROC curve, calibration plot, and diagnostic plots.

## Limitations
Binary survival outcome does not capture survival time.  
Important clinical variables such as treatment and comorbidities are not included.  
Model performance is moderate.

## Future Work
Future work may include survival analysis using Cox regression, inclusion of additional clinical variables, and application of machine learning methods.

## Tools
R programming language  
Libraries include dplyr, ggplot2, pROC, car, ResourceSelection, and corrplot  

## Project Structure
Final-Report.pdf  
README.md  
data folder  
scripts folder  
outputs folder  

## Author
Yajiao Liu
