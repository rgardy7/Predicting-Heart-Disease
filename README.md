# Predicting Heart Disease - Logistic Regression  
## Overview:  
The primary goal of this project was to build a predictive model to identify individuals at high risk of developing coronary heart disease (CHD) within the next ten years. Using a dataset that looks into this, I developed a Logistic Regression model to help with prediciting those that may develop heart disease.  

## Data Source:  
The source of this data comes from a dataset on kaggle called [“Logistic regression To predict heart disease”](https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression/data)  
According to the author of this dataset, the data is from an ongoing cardiovascular study on residents of the town of Framingham, Massachusetts.  
There's 4,238 rows of data with 16 columns.  

## Tools:

**Language:** Python
**Libraries:** Pandas, Numpy, Scikit-learn, Statsmodels, Matplotlib.pyplot, Seaborn
**IDE:** Jupyter Notebook  

## Cleaning The Data:  
During my exploratory data analysis I saw there were missing rows of data and decided to fix this issue through fill the missing data with the median of each column. The reason for doing this is that we have enough data in each row to give us an adequate estimate of where the missing data would likely fall. Having more data in this situation also helps due to this being health related. I think it wouldn't help getting rid of rows of data when we would rather error on the side of caution.  

## Stats Summary
Once I was confident that there was no missing data and no duplicates, I moved on to creating the logit regression. I put together the model and looked at the statistics to get an idea of what the p-values would read as for each variable. To find out what variables would be significant to our data and help the model the most in making the best predicitions it can.  
**Results:** <img width="623" height="451" alt="Logit Regression Results" src="https://github.com/user-attachments/assets/88c9cae9-ced9-4899-9260-35517c8637fc" />  

## Logistic Regression Model  
With the model put together I was able to make a confusion matrix to give a visual of the number of true positives and true negatives the model could predict. To give a sense how accurate the model can be.  
<img width="473" height="396" alt="Confusion Matrix 1" src="https://github.com/user-attachments/assets/b9f52819-58e3-4ad0-81da-f987e142906b" />  
Initially we see that the model will predict a majority of true negatives than true positives. That the model will catch people not having heart disease compared to those that will.  
<img width="602" height="135" alt="Will vs  Will not have heart disease in 10 years" src="https://github.com/user-attachments/assets/f4b814ec-2fdb-4b81-b491-d0af29eb8235" />  
Looking at the scores for accuracy, precision, recall, and f1, it looks like the model does pretty well in predicting based off of the results. Accuracy is high but we shouldn't rely on this metric in this case. Reason being is that the data is skewed towards people not developing heart disease compared to those that will. The point of this model is to predict those individuals will develop heart disease, so in this case relying on the accuracy score can be misleading.  
