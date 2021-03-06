# Credit-Card-Default-Prediction 
The purpose of this project is to conduct quantitative analysis on credit card default risk by using 3 machine learning models with accessible customer data such as clients' personal information, previous billing and payment history, instead of credit score or credit history, with the goal of assisting and speeding up the human decision making process.

## Dataset Source<br>
This dataset contains information on default payments, demographic factors, credit limit, history of payments, and bill statements of credit card clients in Taiwan from April 2005 to September 2005. All the data has been anonymized.

## Project Overview<br>
The analysis consists of 2 parts:
1. Exploratory Data Analysis and Data Preprocessing
2. Machine Learning Modeling and prediction. The detailed notebook of modeling can be found <a href="https://github.com/jiebai999/Credit-Card-Default-Prediction/blob/main/Default_Credit_Card.ipynb">here</a>.

Machine Learning Models Used: 
1. Logistic Regression
2. Random Forest
3. K Nearest Neighbors
4. XGBoost

## Key Parts of EDA and Data Preprocessing
1. The target label set(The customer will likely to be default or not) is imbalanced, only 20% of the target label are default.
2. In order to deal with the imbalanced tartget label, the class weight parameters were tuned in the machine learning modeling.
3. Check the if there are linear relationships between features

## Model Comparison
1. Among these 4 models, Random Forest model and XGBoost model have the highest recall and highest precision, then this two models are the best candidates. If the balance of recall and precision is the most important metric, then Random Forest is the ideal model. Since Random Forest has slightly lower recall but much higher precision than Logistic Regression, we recommend the Random Forest model. 

![image](https://user-images.githubusercontent.com/52012182/155905852-35a8aabf-fbda-4254-b010-80dda15cc70d.png)

2.Among these 4 models, Random Forest model  and XGBoost model have the largest area under the ROC curve. In case if we need to adjust our threshold according to different ecnomic situations, then the Random Forest model and XGBoost are best, since it has the best AUC-ROC score.

![image](https://user-images.githubusercontent.com/52012182/155905895-abac31e7-e3b8-4c8b-8f65-cd6c082f8fdf.png)

## Recommendations Based on Modeling
Below is our suggested recall plot when set threshold recall=0.8. Note the threshold can be adjusted to reach higher recall.
![image](https://user-images.githubusercontent.com/52012182/155748355-24bed546-6313-4a15-9b32-6a4831088593.png)

## Limitations
1. Best model Random Forest and XGBoost can only detect 63% of all the default. 
2. Model can only be served as an aid in decision making instead of replacing human decision.
3. The dataset only contains 30,000 records.
