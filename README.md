# Credit_Risk_Analysis
Using Machine Learning to Evaluate Credit Card Risk

# Overview

Credit card dataset from LendingClub, a peer-to-peer lending services company will be used to evaluate credit card risk.  The dataset will be analyzed using algorithums from the "imbalanced-learn" and "scikit-learn" libraries.  Because the models will not be able to evaluate all features associated with risk, we will evaluate the data will several models and then compare the results.  The evaluations will include the following methods: 
 - oversampling the data with RandomOverSampler
 - oversampling the data with SMOTE
  - undersampling the data with ClusterCentroids
  - Combination over and undersampling with SMOTEENN
  - machine learning with BalancedRandomForestClassifier
  - machine learning with EasyEnsembleClassifier
  
  
# Results

1. Native Random Oversampling - oversampling the data by sampling the minority class instances and adding to the training set until the majority and minority classes are balanced. 
![NativeRandomOversampling](https://user-images.githubusercontent.com/98054953/175446611-e11fcdb0-4b73-4bda-ba07-73e7772ca5bb.png)

