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
During my exploratory data analysis I saw there were missing rows of data and decided to fix this issue through filling the missing data with the median of each column. The reason for doing this is that we have enough data in each row to give us an adequate estimate of where the missing data would likely fall. Having more data in this situation also helps due to this being health related. I think it wouldn't help getting rid of rows of data when we would rather err on the side of caution.  

## Stats Summary
Once I was confident that there was no missing data and no duplicates, I moved on to creating the logit regression. I put together the model and looked at the statistics to get an idea of what the p-values would read as for each variable. To find out what variables would be significant to our data and help the model the most in making the best predicitions it can.  

**Results Summary:**   
<img width="623" height="451" alt="Logit Regression Results" src="https://github.com/user-attachments/assets/88c9cae9-ced9-4899-9260-35517c8637fc" />  

## Logistic Regression Model  
With the model put together I was able to make a confusion matrix to give a visual of the number of true positives and true negatives the model could predict. To give a sense how accurate the model can be.  
<img width="473" height="396" alt="Confusion Matrix 1" src="https://github.com/user-attachments/assets/b9f52819-58e3-4ad0-81da-f987e142906b" />  

Initially we see that the model will predict a majority of true negatives than true positives. That the model will catch people not having heart disease compared to those that will.  
<img width="602" height="135" alt="Will vs  Will not have heart disease in 10 years" src="https://github.com/user-attachments/assets/f4b814ec-2fdb-4b81-b491-d0af29eb8235" />  

Breaking down the model's results, it looks like it does it's job well with high accuracy score of 0.87. The issue though is that the data is skewed towards individuals that won't develop heart disease compared to those that will. This means that the model will more than likely predict someone not to develop heart disease than those that will. We can see this with the low recall score of 0.11, meaning that model is overlooking a lot of cases that people could be developing heart disease. This would be dangerous to have this model set the way it is because it means that potentially people that may actually be developing heart disease in the next 10 years wouldn't be caught.  

## Fixing the Skewed Issue  
The reason that this issue needs to be fixed is becuase in healthcare you'd rather err on the side of caution. If someone seems healthy but could benefit from having more tests done to make sure that there is no underlying issues that should be made aware, then it would be best to modify the model to be more cautious. Since the proportions of the data skew more to the side of people not developing a heart disease in the next 10 years, I'll add more weight to the classes that will develop heart disease in the next 10 years. What this will do is make sure that the people who will develop heart disease are better represented in the model and make sure people are getting the care needed.

## Multicollinearity  
There also is some issues with multicollinearity within the model and to fix this issue I ended up dropping a few variables that were highly correlated with each other to help make the model be more dependable. With those variables dropped from the model I began to perform the final logistic regression results.  

## Final Lostic Regression Model Results  
<img width="484" height="389" alt="Confusion Matrix 2" src="https://github.com/user-attachments/assets/9b15e993-701d-4097-92e8-3352ed13f969" />  

Starting with the confusion matrix you can see there's still a high number of true negatives in the top left hand corner of the matrix. The biggest difference you'll see is there's more true positives on the bottom right of the matrix and false postives at the top right. Overall this is good becuase it means the model is taking in more consideration for the minority of the data to be able to catch more people that may be developing heart disease in the next 10 years. Though there's a larger number of false positives, it's okay because it means that people are getting screened more in order to be sure that they either are or aren't developing heart disease.  

<img width="517" height="395" alt="ROC Curve 2" src="https://github.com/user-attachments/assets/660f7c9e-524c-4ac3-8557-80be355af49f" />  

The ROC Curve is also showing decent results. With AUC being at a 0.68 which is better than the previous AUC results showing only 0.55. Showing that the model is useful in catching people developing heart disease in the next 10 years.  

<img width="787" height="149" alt="Will vs  Will not have heart disease in 10 years final results" src="https://github.com/user-attachments/assets/e7ce1929-f5c2-4ac7-904e-b6442c09da3b" />  

Finishing off looking at our metrics, accuracy looks to be still in a good position at 0.66. Our recall score is now at 0.71 meaning that the model is good at finding most of the positive cases of people developing heart disease compared to before when the recall score was at 0.11. Precision did decline down to 0.25 meaning that there's more false positives within the model. As said before though, this is okay because we'd rather err on the side of caution and make sure people are getting tested enough to make sure they either are or aren't developing heart disease.
