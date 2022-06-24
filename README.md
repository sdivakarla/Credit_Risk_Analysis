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
 - Accuracy rate was 64%
 - High risk precision was 1% and Low Risk precision was 100%
 - Recall(sensitivity) was 59% for high risk and 69 % for low risk
 - F1 scores were 2% for high risk and 82% for low risk

2. SMOTE - oversampling the minority data with nearest neighbor interpolation to increase the number of samples. 
![SMOTEOversampling](https://user-images.githubusercontent.com/98054953/175547415-b71945e2-ef47-4fa2-b014-54b04245b6d8.png)
 - Accuracy rate was 63.7%
 - High risk precision was 1% and Low Risk precision was 100%
 - Recall(sensitivity) was 63% for high risk and 64 % for low risk
 - F1 scores were 2% for high risk and 78% for low risk

3. ClusterCentroids - undersampling the majority data to approximate the number of minority samples 
![ClusterCentroids](https://user-images.githubusercontent.com/98054953/175547572-b2f1be75-e572-4766-9305-461da445c9c0.png)
 - Accuracy rate was 63.7%
 - High risk precision was 1% and Low Risk precision was 100%
 - Recall(sensitivity) was 61% for high risk and 45% for low risk
 - F1 scores were 1% for high risk and 62% for low risk
4. SMOTEEN - Combination sampling with undersampling in the area of overlap and then nearest neighbor filling in data. 
![SMOTEEN](https://user-images.githubusercontent.com/98054953/175547742-fe6a25e4-6ca3-487e-af0c-3fd121f7e7c6.png)
 - Accuracy rate was 52.9%
 - High risk precision was 1% and Low Risk precision was 100%
 - Recall(sensitivity) was 70% for high risk and 87% for low risk
 - F1 scores were 6% for high risk and 73% for low risk

5. BalancedRandomForestClassifier - machine learning with 100 iterations of Random Forest models. 
![BalancedForest](https://user-images.githubusercontent.com/98054953/175547883-f0d13402-54bb-4d01-a373-e525cf5555c5.png)
 - Accuracy rate was 78.9%
 - High risk precision was 3% and Low Risk precision was 100%
 - Recall(sensitivity) was 70% for high risk and 87% for low risk
 - F1 scores were 16% for high risk and 93% for low risk
 
6. EasyEnsembleClassifer - machine learning using the Easy Ensemble model
![AdABoost](https://user-images.githubusercontent.com/98054953/175548018-6cabb798-b20e-4dd3-8dd1-730d8cdbeebf.png)
 - Accuracy rate was 93.1%
 - High risk precision was 9% and Low Risk precision was 100%
 - Recall(sensitivity) was 92% for high risk and 94% for low risk
 - F1 scores were 16% for high risk and 97% for low risk

# Analysis

Running multiple models allows for comparision of "fit" of the models to the dataset and the ability of the models to explain the variability.  The models are more robust predictive tools if the models are able to fit the variability and then may be used on new data as it is collected, assuming the distribution and variability are similar to the original dataset. 

Due to the disparity in the sample numbers in the two categories, different analysis techniques were used to evaluate the data.  The first four models (which utilized oversampling, undersampling and a combination technique) all had accuracy levels of less than 65%, poorly fit the high risk data and sensitivity values that maxed out at 87% with the SMOTEEN model. 

The machine learning models used ensemble classifers trained on balanced bootstrap samples.  The ensemble based models fit the high risk data better and had higher sensitivity and F1 scores, indicating that the false positive rates were lower and models better explained the variability in the data.  The Easy Ensemble Classifer outperformed the Balanced Random Forest Classifer and is the model that should continue to be refined as more data is collected and evaluated. 

