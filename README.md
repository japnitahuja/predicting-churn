# Customer Churn Prediction using Machine Learning

This repository contains the implementation and analysis of a machine learning project focused on predicting customer churn in the banking sector. Customer churn, the phenomenon of customers leaving a service, can significantly impact a bank's operations and revenues. In this project, we explore the use of various machine learning algorithms to predict customer churn, with the goal of assisting banks in proactively addressing customer attrition. Three classification algorithms - XGBoost, neural networks, and logistic regression - are employed and compared to identify the most effective model for predicting customer churn.

## Dataset

The Bank Turnover Dataset, obtained from Kaggle, contains information about customers who may or may not leave the bank within the next six months. The dataset comprises 10,000 records and 13 features that can be utilized to predict the customer churn class label.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/d1e2a379-66d7-420b-8187-568e9c981113)


## Data Preprocessing
The dataset is carefully preprocessed to ensure its quality and suitability for modeling. 

- Missing values: No missing values are present.
- Duplicate and low variance data: No duplicated rows or columns with low variance are identified. 
- Irrelevant columns: Customer ID, row number, and surname are dropped.
- Categorical data: One hot encoding is used to transform categorical columns of gender and geography into numerical format.
- Feature scaling: The numerical features of credit score, balance, estimated salary and age are scaled using min-max scaler.

### Feature Engineering
It was determined that no two features shared high correlation for aggregation using PCA.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/b9c48146-3e35-4783-9841-e73e810087e6)


### Outlier Analysis
Distribution plots, including histograms and box plots, are employed to detect outliers in numerical features. Credit score, balance, and estimated salary are examined, with credit score showing some outliers. Given the context, these outliers are retained as they could be valid data points.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/55eb215a-0102-43ef-823b-c547dc7a6740)



## Model Comparison

### Neural Network

#### Hyperparameter Tuning

The neural network architecture is shown in figure 14. The input layer consists of 13 neurons for each feature. This is followed by the hidden layer at 9 neurons and the output layer at 1 neuron for binary classification. In the hidden layer, 9 neurons were chosen based on the complexity of the problem. The size of the dataset is not that big, thus to avoid overfitting, a simpler neural network architecture was chosen. This was confirmed through a trial and error method by comparing the
accuracies achieved at different numbers of neurons in the hidden layer.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/ad9189e5-5c80-4686-ae26-f5f61ba2637b)


#### Results
The neural network model achieves competitive results in predicting customer churn, with a particular focus on identifying customers who will stay. The testing accuracy was 86.09% for this model. It exhibits decent accuracy and precision, but its recall remains relatively low, suggesting room for improvement in identifying actual "churn" cases.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/00a46d6e-3ead-4b1f-bf57-5c5b3d80810e)


### XGBoost

#### Hyperparameter Tuning

The maximum depth of the trees in Xgboost is identified through a trial and error method by comparing the accuracies achieved at different maximum depth. Maximum test set
accuracy was seen at 4 depth. Moreover, the learning rate was kept 0.01 to avoid overshooting and to make sure that it doesn’t take too long to converge.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/d5e31bf3-2505-4d2b-8544-69802caf3a91)


#### Results

XGBoost achieves a testing accuracy of 86.57%. It outperforms the other models in identifying customers who will stay, though there is room for improvement in predicting customers who might leave.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/aae39b16-7c98-4217-ae23-82b6dc77d59f)


### Logistic Regression

#### Results
Logistic regression achieves a testing accuracy of 80.96%. While it performs well in predicting customers who stay, it lags behind the neural network and XGBoost in identifying potential churners.

![image](https://github.com/japnitahuja/predicting-churn/assets/10168783/45af792a-7f63-40bd-b24e-d0b8f4601d42)


## Conclusion

Predicting customer churn is of paramount importance for banks. In this project, machine learning techniques are harnessed to forecast customer churn. While all three models show promising results, XGBoost stands out with its superior accuracy in predicting customers who will stay. As the banking sector continues to evolve, accurate churn prediction will enable proactive strategies to retain customers and maintain competitiveness.
