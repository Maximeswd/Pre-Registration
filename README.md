# Pre-Registration
 Pre-Registration of my Master Thesis Project

### Research Project: Predicting the Time to Fill Vacancies: A Pre-registered Comparison of Four Common Feature Encoders

#### Data Cleaning & Pre-processing
Data cleaning and pre-processing are of high importance. Therefore, the following steps were conducted.
1.	Removing variables: Duplicates, irrelevant observations (applicants that were not hired, and pipeline requisitions), columns that contained more than 50% missing values, identifying variables and variables within the time frame of our target variable were removed. 
2.	Imputation: Missing values were imputed through the use of the K-Nearest-Neighbours imputation algorithm. This is to be conducted after the split to prevent target leakage as the variables will first be label encoded, after which the MinMax scaler will be utilized, followed by inverse transformation of all the variables to the original format. 
3.	Not removed: Outliers were not removed as the hypothesis is reflected by the underlying argument that quantile encoding is more robust against outliers and skewed tails which is ought to be tested. 

#### Feature Engineering
As feature engineering is an important part of every machine learning project, this research will utilize different feature engineering techniques. There are three key feature engineering parts of the thesis:
1.	Date variables: All the date variables that take place before the predicted time period are first used to calculate the difference between all those date variables. Secondly, all the date variables before the predicted time period are then separated into day, month and year.
2.	Count variables: The manually computed count variables consist of similar counts which is calculated by calculating how many similar requisitions are opened in the previous month. Since the date of opening is before out predicted time period, this will not cause data leakage. The second count variable is calculated by counting all the requisitions that are opened by the same recruiter in the previous month. As both of these count variables are expected to have some value for predicting the TTF.
3.	Categorical variables: All categorical variables will be transformed by four different Encoding Techniques, namely One-Hot Encoding, Target Encoding, Quantile Encoding, and Catboost Encoding. 

#### Encoder Comparison
The feature encoding techniques will be compared through the Wilcoxon t-test, which is used to compare two gradient boosted decision tree models (LightGBM) on a single sample to assess whether their population means differ. 


