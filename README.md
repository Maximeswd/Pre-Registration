# Pre-Registration
 Pre-Registration of my Master Thesis Project: Behavioural Data Science

### Research Project: Predicting the Time to Fill Vacancies: A Pre-registered Comparison of Four Common Feature Encoders

#### Data Collection
The data is already collected by the company and thus no further data collection is needed. 

#### Hypotheses
Hypothesis 1: Regarding the low-cardinality variables, Catboost encoding will outperform One-Hot encoding, Quantile encoding and Target encoding. One-hot encoding will outperform Quantile encoding and Target encoding. Quantile encoding will outperform Target encoding. 

Hypothesis 2: Regarding the high-cardinality variables, Catboost encoding will outperform One-Hot encoding, Quantile encoding and Target encoding. Quantile encoding will outperform One-Hot encoding, and Target encoding. Target encoding will outperform One-Hot encoding. 

Hypothesis 3: Regarding all the categorical variables, Catboost encoding will outperform One-Hot encoding, Quantile encoding and Target encoding. Quantile encoding will outperform One-Hot encoding, and Target encoding. Target encoding will outperform One-Hot encoding. 

#### The target variable
The target variable is the Time-To-Fill, which is calculated by taking the difference between the date that a vacancy is opened and the date that the applicant is hired. 

#### Data Cleaning & Pre-processing
Data cleaning and pre-processing are of high importance. Therefore, the following steps were conducted.
1.	Removing variables: Duplicates, irrelevant observations (applicants that were not hired, and pipeline requisitions), columns that contained more than 50% missing values, identifying variables and variables within the time frame of our target variable. 
2.	Imputation: Missing values were imputed through the use of the K-Nearest-Neighbours imputation algorithm. This is to be conducted after the split to prevent data leakage as the variables will first be label encoded, after which the MinMax scaler will be utilized, followed by inverse transformation of all the variables to the original format. 
3.	Not removed: Outliers were not removed as the hypothesis is based on the underlying argument that quantile encoding is more robust against outliers and skewed tails which is ought to be tested. 

#### Feature Engineering
As feature engineering is an important part of every machine learning project, this research will utilize different feature engineering techniques. There are three key feature engineering parts of the thesis:
1.	Date variables: All the date variables that take place before the predicted time period are first used to calculate the difference between all those date variables. Secondly, all the date variables before the predicted time period are then separated into day, month and year.
2.	Count variables: Two count variables are engineered as both of these count variables are expected to have some value for predicting the TTF. The first consists of 'similar counts' by calculating how many similar requisitions are opened in the previous month. Since the date of opening is before out predicted time period, this will not cause data leakage. The second count variable conists of 'hire counts' which is calculated by taking all the requisitions that are opened in respect to the same recruiter in the previous month. 
3.	Categorical variables: All categorical variables will be transformed by four different Encoding Techniques, namely One-Hot Encoding, Target Encoding, Quantile Encoding, and Catboost Encoding. 

#### Encoder Comparisons
The feature encoding techniques will be compared through the Wilcoxon paired two-sided tests, which is used to compare two gradient boosted decision tree models (LightGBM) on a single sample to assess whether their MAE scores differ. The tests are paired, because the same sample is used for all the encoders. The tests are two sided so if the two-sided p-value of the Wilcoxon paired test was <.05, the two encoding techniques compared are significantly different. Therefore, if the p-value is significant, the encoding technique with the lowest MAE is found to be significantly better performing than the other encoding technique. 


