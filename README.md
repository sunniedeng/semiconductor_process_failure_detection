# semiconductor_process_failure_detection
The dataset presented in this case represents a selection of features where each example represents a single production entity with associated measured features and the labels represent a simple pass/fail yield for in house line testing, and associated date time stamp. Where –1 corresponds to a pass and 1 corresponds to a fail and the data time stamp is for that specific test point.

Firstly, I cleaned data: 
  1. Drop columns which have more than 50% null values
  2. Drop 0 variance columns
  3. Fill null values using KNN imputer
Secondly, because there were 591 features and only 1567 examples, I used boruta to select 8 features out of 591 features.
Thirdly, because the dataset is imbalanced (14:1), I used resampling technique on train set.
At last, I tried several algorithms, and achieved best result by random forest tuning with randomized search CV. 
We want to detect failures so we will focus on recall. Recall is 0.90. Auc-ROC score is 0.8. 
