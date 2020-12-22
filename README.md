# Data-Preprocessing
Codes and notes of data preprocessing for ML model development

## Definition
- Preparation of data directly after accessing it from a data source. 
- This step is done before the interactive analysis of data begins. 

## 1. Data Cleaning 

###### Missing data
-Removing: Rule of thumb: If more than 50% of values are missing for any of the database rows or columns, you have to delete the whole row/column unless it is possible to fill in the missing values.
-Imputation (replacement of missing observations by using statistical algorithms).
-Binning (count-based, handling of missing values as its own group, …)

For categorical features, you can do things like:
* 		Mode filling: Fill missing values with the most popular/frequent/modal class.
* 		Temporal filling (forward or backward fill): Fill missing values with the preceding value (top-down) or with the succeeding value (bottom-up).
* 		Encoding and fill: In this method, you can encode the values using different strategies, and then fill with either the mean, mode, or the median.

For numerical features, we can also do things like:
* 		Filling with mean, mode, or median.
* 		Temporal filling (backward or forward filling).
* 		Use machine learning models: Train a machine learning model to learn the most appropriate fill values.

* Incomplete records 
particular character, such as a question mark.

* Noisy data
-Duplicated data. removal of duplicates.

* Outliers or anomalies
Unexpected values often surface in a distribution of values, especially when working with data from unknown sources which lack poor data validation controls.

* Mixture of data values
Mixed data value such as girl and women which hold the same meaning 
Check unique value for categorical class.
Use: df[“column name”].value_counts()

* Improperly formatted/structured data
Data sometimes needs to be extracted into a different format or location. 
A good way to address this is to consult domain experts or join data from other sources.

* Inconsistent values and non-standardized categorical variables
Often when combining data from multiple sources, we can end up with variations in variables like company names or states. For instance, a state in one system could be “Texas,” while in another it could be “TX.”  Finding all variations and correctly standardizing will greatly improve the model accuracy.

* Limited or sparse features/attributes
Feature enrichment, or building out the features in our data often requires us to combine datasets from diverse sources. Joining files from different systems is often hampered when there are no easy or exact columns to match the datasets. This then requires the ability to perform fuzzy matching, which could also be based on combining multiple columns to achieve the match. For instance, combining two datasets on CUSTOMER ID (present in both data datasets) could be easy. Combining a dataset that has separate columns for CUSTOMER FIRST NAME and CUSTOMER LAST NAME with another dataset with a column CUSTOMER FULL NAME, containing “Last name, First name” becomes more tricky.

* Sensitive data
Anonymize or remove the data completely.

2.Data Transformation
* Scaling (Normalization): The preprocessed data may contain attributes with a mixtures of scales for various quantities such as dollars, kilograms and sales volume. Many machine learning methods like data attributes to have the same scale such as between 0 and 1 for the smallest and largest value for a given feature. Consider any feature scaling you may need to perform.
* Decomposition: There may be features that represent a complex concept that may be more useful to a machine learning method when split into the constituent parts. An example is a date that may have day and time components that in turn could be split out further. Perhaps only the hour of day is relevant to the problem being solved. consider what feature decompositions you can perform.
* Aggregation: There may be features that can be aggregated into a single feature that would be more meaningful to the problem you are trying to solve. For example, there may be a data instances for each time a customer logged into a system that could be aggregated into a count for the number of logins allowing the additional instances to be discarded. Consider what type of feature aggregations could perform.

Normalization
Discretization

Transformations (normalisation, standardisation, scaling, pivoting, ...)

3.Data Reduction
Reducing the number of features by creating lower-dimension, more powerful data representations using techniques such as PCA, embedding extraction, and hashing.Dimensionality reduction

4.Data Selection
-Data Replacement (cutting, splitting, merging, ...)

-Weighting and Selection (attribute weighting, automatic optimization, ...)

-Feature selection. Selecting a subset of the input features for training the model, and ignoring the irrelevant or redundant ones, using filter or wrapper methods. This can also involve simply dropping features if the features are missing a large number of values.

-Data selection. Selecting data points from the input dataset to create training, evaluation (validation), and test sets. This process includes techniques for repeatable random sampling, minority classes oversampling, and stratified partitioning.

-Data Partitioning (create training + validation + test data set, ...)

## Reference:
1. https://cloud.google.com/solutions/machine-learning/data-preprocessing-for-ml-with-tf-transform-pt1
2. https://medium.com/better-programming/data-preprocessing-for-machine-learning-3822ace03ae6
3. https://www.infoq.com/articles/ml-data-processing/
4. https://www.datarobot.com/wiki/data-preparation/
5. https://heartbeat.fritz.ai/a-practical-guide-to-feature-engineering-in-python-8326e40747c8
