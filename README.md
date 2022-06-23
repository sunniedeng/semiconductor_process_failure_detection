# semiconductor_process_failure_detection
It a real dataset from semiconductor industry.

The dataset presented represents a selection of features where each example represents a single production entity with associated measured features and the labels represent a simple pass/fail yield for in house line testing, and associated date time stamp. Where –1 corresponds to a pass and 1 corresponds to a fail and the data time stamp is for that specific test point.

Firstly, I cleaned data: 
  1. Drop columns which have more than 50% null values
  2. Drop 0 variance columns
  3. Fill null values using KNN imputer

Secondly, because there were 591 features and only 1567 examples, I used boruta to select 8 features out of 591 features.

Thirdly, because the dataset is imbalanced (14:1), I used resampling technique on train set.

At last, I tried several algorithms, and achieved best result by random forest tuning with randomized search CV. I ranked 8 features by feature importance. 
We want to detect failures so we will focus on recall. Recall is 0.90. Auc-ROC score is 0.8. 

In fab, you can have very limited data, e.g. in this case only 1567 examples collected. We need to focus on the most important metric (recall in this case) and sarcrifice others to a reasonable extent. If we collect more data, I believe we can improve the model further.
