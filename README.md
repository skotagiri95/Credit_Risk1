# Credit_Risk1

## Objectives
The goals of this challenge are:

- Implement machine learning models
- Use Credit Risk *Resampling Techniques* to address class imbalance
- Evaluate the performance of machine learning models

**Using `imbalanced-learn` library to resample the data and build and evaluate logistic regression classifiers using the resampled data**

Oversample the data using the RandomOverSampler and *SMOTE* algorithms.
Undersample the data using the cluster centroids algorithm.
Use a combination approach with the *SMOTEENN* algorithm.
For each of the above you will find:

1. Train a logistic regression classifier (from *Scikit-learn*) using the resampled data.
2. Calculate the balanced accuracy score using balanced_accuracy_score from sklearn.metrics.
3. Generate a confusion_matrix.
4. Print the classification report (`classification_report_imbalanced from imblearn.metrics`).
___
*`target = ["loan_status"]`*
+ Low-Risk  68,470
- High-Risk    347

Finding that the data from LendingClub is imbalanced with 68,470 Low-Risk applicants vs 347 High-Risk we used Resampling Techniques and various Machine Learning models described below. This will help us further fine-tune by training our machine learning models with balanced data. 

# Oversampling
**Credit Risk Resampling using Naive Random Oversampling**
+ Low-Risk  51,366
- High-Risk 51,366

**Balanced Accuracy Score: 0.644**

## Confusion Matrix
---
---
**
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
                       Model Prediction 
                    No Default   |  Default (1) |
                        (0)      |              |
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
Actual              |             |             |
Loan    no default  |   TN        |    FP       |
Status      (0)     |             |             |
---
           default  |   FN        |    TP       |
            (1)     |             |             |
---
- TN = True Negative
+ FP = False Positive
- FN = False Negative
+ TP = True Positive

From the confusion matrix results, we can see a large number of false positives (28),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.72 and Low-Risk = 0.57 applications, which is indicative of the large number of false negatives. The F1 score is also low (0.72)

**SMOTE Oversampling**
+ Low-Risk:  51,366
- High-Risk: 51,366

**Balanced Accuracy Score: 0.644**
From the confusion matrix results, we can see a large number of false positives (37),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.63 and Low-Risk = 0.69 applications, which is indicative of the large number of false negatives. The F1 score is also low (0.82) but **SMOTE F1 score 0.82  is better than Random Oversampling f1 0.72**

**ClusterCentroids Undersampling**
+ Low-Risk:  246
- High-Risk: 246

**Balanced Accuracy Score: 0.533**
From the confusion matrix results, we can see a large number of false positives (34),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.66 and Low-Risk = 0.40 applications, which is indicative of the large number of false negatives. The F1 score is also low (0.52) but **SMOTE F1 score is also better than Undersampling**

**SMOTEENN Combined Oversampling and Undersampling**
+ Low-Risk:  68,460
- High-Risk: 62,011

**Balanced Accuracy Score: 0.644**
From the confusion matrix results, we can see a large number of false positives (28),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.72 and Low-Risk = 0.57 applications, which is indicative of the large number of false negatives. The F1 score is also low (0.72) but **SMOTE F1 score 0.82  is also better than Combined Oversampling and Undersampling f1 0.72**

## Ensemble Learners
**Balanced Random Forest Random Oversampler**
+ Low-Risk:  51,366
- High-Risk: 51,366

**Balanced Accuracy Score: 0.650**
From the confusion matrix results, we can see a large number of false positives (31),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.69 and Low-Risk = 0.61 applications, which is indicative of the large number of false negatives. The F1 score is also low (0.76) but  **SMOTE F1 score 0.82 is also better than Random Forest 0.76**

**Balanced Random Forest StandardScaler**
+ Low-Risk:  17,167
- High-Risk: 38

**Balanced Accuracy Score: 0.678**
From the confusion matrix results, we can see a large number of false positives (65),  which indicates an unreliable positive classification. The recall is also low High-Risk = 0.36 and Low-Risk = 1.0 applications, which is indicative of the large number of false negatives. The F1 score is also low (1.0), it seems we have over fit this algorithm and requires further analysis.

**Final Reccomendation
After utilizing Ensemble Learners, StandardScaler, Random Sampler, SMOTE Oversampler, Cluster Centroids Undersampler, and SMOTEENN Combined Sampler we find SMOTE Oversampler as the best Machine Learning algorithm providing the better results with an F1 score of 0.82. However, this will require further analysis.

