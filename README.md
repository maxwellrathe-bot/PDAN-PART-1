Medical Insurance Cost Prediction Report 
Linear Regression Analysis for Medical Aid Scheme 
Date: March 29, 2026 | Version: 1.0 
Executive Summary 
This report presents a comprehensive analysis to develop a predictive model for medical insurance 
charges. The model helps tailor costs according to client demographics and lifestyle factors. 
Key Finding: Smokers pay approximately $23,500 more annually than non-smokers, representing a 
274% increase in average insurance costs. 
Model Performance: The linear regression model explains 78.1% of the variance in medical charges, with 
smoking status, age, and BMI identified as the strongest predictors. 
1. Introduction and Objectives 
1.1 Business Problem 
The medical aid scheme requires a data-driven approach to: 
Predict medical insurance charges based on client characteristics 
Identify key factors driving healthcare costs 
Develop fair, risk-based premium structures 
Implement targeted wellness programs 
1.2 Analysis Objectives 
1. Evaluate dataset suitability for linear regression 
2. Identify patterns and relationships in the data 
3. Develop an accurate predictive model 
4. Provide actionable business recommendations 
2. Data Overview and Preparation 
2.1 Dataset Description 
Aspect 
Details 
Source 
US Medical Insurance Dataset (Kaggle) 
Records 
1,338 observations 
Features 
6 variables (3 numerical, 3 categorical) 
Target 
Medical charges (continuous variable) 
Description 
Type 
2.2 Feature Description 
Feature 
age 
Numerical 
Age of the client (18-64 years) 
sex 
Categorical 
Male/Female 
bmi 
Numerical 
Body Mass Index (15-53) 
children 
Numerical 
Number of dependents (0-5) 
smoker 
Categorical 
Smoking status (Yes/No) 
Feature 
region 
Type 
Categorical 
Description Geographic region 
Target 
charges 
Medical insurance charges ($1,121 - $63,770) 
2.3 Data Quality Assessment 
 
 
 
 
3. Exploratory Data Analysis (EDA) 
3.1 Distribution of Medical Charges 
Metric 
Mean Charge 
Value 
$13,270 
Median Charge 
$9,382 
Range 
$1,121 - $63,770 
Skewness 
1.52 (right-skewed) 
Key Finding: Right-skewed distribution - most charges cluster at lower values with significant outliers 
above $40,000. 
Distribution 
3.2 Categorical Features Analysis 
Category 
Sex 
Female: 662, Male: 676 
Key Insight 
Smoker 
Non-smoker: 1,064, Smoker: 274 
Balanced representation 
20% of clients are 
smokers 
Region 
Southeast: 364, Southwest: 325, Northwest: 325, 
Northeast: 324 
Even regional distribution 
3.3 Correlation Analysis 
 
 
Feature Correlation Strength 
smoker_yes 0.79 Strong Positive 
age 0.30 Moderate Positive 
bmi 0.20 Weak-Moderate Positive 
children 0.07 Weak Positive 
Key Insight: Smoking is the dominant predictor, with no multicollinearity issues. 
 
4. Model Development 
 
4.1 Feature Selection (P-values) 
Featureconst Coefficient-$11,838 P-value0.000 
✓ 
Significant 
 
age $257 0.000 ✓ 
bmi $330 0.000 ✓ 
children $450 0.000 ✓ 
sex_male -$131 0.037 ✓ 
smoker_yes $23,485 0.000 ✓ 
region_northwest -$353 0.028 ✓ 
region_southeast $783 0.000 ✓ 
region_southwest -$940 0.000 ✓ 
 
4.2 Model Equation 
Charges = -$11,838 + $257×age + $330×bmi + $450×children - $131×sex_male + $23,485×smoker_yes - 
$353×region_northwest + $783×region_southeast - 
$940×region_southwest 
 
 
 
 
 
 
 
5. Model Evaluation 
5.1 Performance Metrics 
Metric 
Training Set 
Testing Set 
Interpretation 
R-squared 
0.749 
0.781 
MAE 
Model explains 78.1% of variance 
$4,153 
$4,150 
Average error of $4,150 
RMSE 
$5,962 
$6,050 
Penalizes larger errors 
5.2 Residual Analysis 
Residual Statistics: 
Mean: $1.62 (close to 0 - unbiased predictions) 
Standard Deviation: $6,050 
Skewness: 0.48 (slight positive skew) 
 
 
 
 
6. Business Recommendations 
6.1 Immediate Actions (0-6 months) 
Smoking Cessation Program 
Premium discounts up to $10,000/year for non-smokers 
Free nicotine replacement therapy and counseling 
Expected ROI: 300% reduction in smoking-related claims 
Target: Convert 30% of smokers ($2M annual savings) 
Age-Based Premium Structure 
Create age-tiered pricing (18-30, 31-45, 46-60, 61+) 
Preventive care programs for older members 
Fairer premiums, reduced adverse selection 
BMI Management Initiative 
Gym memberships (20-30% discount) 
Nutrition counseling services 
Premium reductions for BMI reduction milestones 
6.2 Medium-term Strategies (6-12 months) 
Regional Pricing Optimization: Adjust premiums based on regional cost variations 
Family Plan Restructuring: Create tiered family plans (0-2 children, 3+ children) 
Data Collection Enhancement: Family history, exercise, diet, claims history 
6.3 Expected Financial Impact 
Initiative 
Smoking Cessation (30% conversion) 
Annual Savings Estimate 
$2,000,000 
BMI Management (10% reduction in 20% of members) 
$500,000 
Regional Optimization 
Total Estimated Savings 
$250,000 
$2,750,000 
7. Model Limitations and Risks 
Limitation 
Impact 
Mitigation 
22% unexplained variance 
Missing factors affect predictions 
Collect additional features 
US-based data 
May not generalize to South Africa 
Validate with local data 
Linear assumptions 
May miss complex interactions 
Outlier sensitivity 
Test non-linear models 
High-cost cases underpredicted 
Ensemble methods 
Business Risks 
 
 
 
8. Conclusion 
8.1 Summary of Achievements 
✓ Successfully developed predictive model explaining 78.1% of variance 
✓ Identified smoking as the dominant cost driver ($23,485 premium) 
✓ Quantified impacts of age, BMI, children, and region✓ Provided actionable business 
recommendations 
8.2 Key Takeaways 
1. Smoking cessation offers the highest ROI opportunity 
2. Age and BMI are significant but manageable risk factors 
3. Data quality is excellent with no missing values 
4. Model performs well for typical cases ($5,000-$25,000) 
Timeline 
8.3 Next Steps 
Phase 
Focus 
Phase 1 
0-3 months 
Deploy model, launch cessation program 
Phase 2 
3-6 months 
Collect features, validate locally 
Phase 3 
6-12 months 
Test non-linear models, dashboard 
Appendices 
Appendix A: Model Technical Details 
Algorithm: Ordinary Least Squares (OLS) 
Linear Regression 
Training Data: 1,070 records (80%) 
Test Data: 268 records (20%) 
Features: 8 (after one-hot 
encoding) Random Seed: 42 
(for reproducibility) 
Appendix B: Software and Libraries Used 
 
 
 
 
 
 
