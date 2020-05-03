# Credit_Risk1

## Objectives
The goals of this challenge are:

- Implement machine learning models
- Use Credit Risk *Resampling Techniques* to address class imbalance
- Evaluate the performance of machine learning models

## Analysis

The models utilized in this analysis produced low precision in predicting high risk loans, 0.01. This tell us there are many false positives in the dataset. Based on the fact that the models have 100% precision in detecting low risk applications, it can be concluded none of the models were the best fit for the data. 

However if we were to choose, the random oversampling method showed a pretty decent recall rate - 70% in predicting high risk applicants. And undersampling being the most ineffective - 48.

credit_risk_ensemble
The ensemble models performance is much better than the latter ones. Even though, AdaBoost showed a pretty low precision in identifying high risk applications, it showed a nice recall rate. Which tells us high risk is well detected but there is also some amount of false negatives. Plus, the AdaBoost's accuracy score is great, 0.90.

Balanced Random Forest managed to get quite a low accuracy score, compared to AdaBoost - 0.67. Its precision rate is very high, the recall rate of finding high risks being signifcantly lower - 0.35. Which says the model fails at detecting the class well. Has perfect metrics in classyfying the low risk applications, 100% in both precision and sensitivity.

## Final Reccomendation

After utilizing Ensemble Learners, StandardScaler, Random Sampler, SMOTE Oversampler, Cluster Centroids Undersampler, and SMOTEENN Combined Sampler we find SMOTE Oversampler as the best Machine Learning algorithm providing the better results with an F1 score of 0.82. However, this will require further analysis.

