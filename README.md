# Credit Card Fraud Detection
Project Summary: To use machine learning models to detect credit card fraud cases from various transaction details. The dataset used in this project is openly available on github [here](https://www.kaggle.com/mlg-ulb/creditcardfraud)

Usually feature selection is done before fitting the model but here we have selected the model first and applied feature selection on the model which provides best results when all the features are selected. There are 2 reasons behind it - 
1. Due to privacy issues the names of the columns are unknown. They are numbered from V1 to V28.
2. Forward selection and Backward elimination methods of feature selection were ineffective.

### Selecting Best Model
In this section, we have done vizualization to understand the data better and applied all the machine learning models to find the best fitting model. PCA has been applied on all the features to scale the values. We picked Random Forest, KNN and Naive Bayes classifier. 

If we talk in practicality, the KNN classifier is not effecient here. Here the model will be deployed in real time and we need very quick results, whereas KNN performs huge amount of computations while predicting and hence needs a lot of time.

For Random Forest we performed hyperparameter tuning using both grid search and random search but didn't get better results. We also went a step ahead and applied Extra Tree Classifier and ADA boosting but still the results didn't improve much.

Finally we selected the Naive Bayes model. It is already well known to be used in this field. Though it predicted around 2% correct transactions as fraud but it was out best shot at catching fraud transactions which is the aim. Further, you will see that we made the predictions much more better using feature selection.

### Feature Selection
In this section we applied various feature selection methods on our selected Naive Bayes model to make predictions better. We applied PCA, LDA and KernelPCA but results weren't good. Finally we applied a score comparison method to select features. Using this method we were able to select 18 best features and decreased the former 2% correct transactions error to less than 1%.

### Ensemble Methods
Finally we applied some ensemble methods on our classifier to boost the results. We applied Bagging, ADA Boost and Bagging on ADA Boost Classifier. Bagging gave us the best results by reducing the error more.

## Conclusion: From this research work we got the best results by using Naive Bayes Model with Sequential Feature Selector from mlxtend which gave us 18 best features and finally applying bagging ensemble method.
