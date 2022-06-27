# ames-housing
A linear regression model that predicts housing prices in Ames, Iowa

## Problem Statement:
How can we best create a linear model to predict sale price of homes based on a given set of data

---
## Target Audience:
This report is intended for colleagues and teammates working together to tackle this problem

---
## Sources:
Pardoe , I. (2008), “Modeling home prices using realtor data”, Journal of Statistics Education Volume 16, Number 2 (2008)

---
## Data Dictionary:
Data dictionary for this dataset can be found [here](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

---
## Analysis:
Our model gave a best R<sup>2</sup> scores of 0.905 and 0.907 for our train and test splits respectively. This corresponded to a mean squared error of 21939. However our mean squared error rose significantly to when applying our model to the final test set. The final model was a lasso linear model with a standard scalar applied to the training data. Ridge regression fit similarly to lasso but ordinary least square gave significantly worse results.     

Iterations of our model found that the best scores scores were achieved when providing the lasso fit with the most possible data. For this reason the standard scalar was chosen over utilizing recursive feature elimination. 

Further analysis of plots of our predictions showed that our residuals were fairly well distributed however our predictions were noticeably low on the low end and high end of prices giving a quadratic shape to our scatter plot. 

---
## Conclusion:
The greatest takeaway of this project was the importance and priority of data cleaning. Our initial approach was to focus on the data we expected to give the best model and to clean data along the way. However this created rabbit holes of trying to get overly creative with specific pieces of data (such as trying to give a numeric score to neighborhoods) which ultimately led to not all of the data being properly cleaned and gave less time to experiment with different amounts of features. 

Given the ultimate goal of scoring our model in kaggle we also sacrificed best practices in the interest of pursuing the best possible mean squared error on our training set. Our final model included a number of features that were colinear and statistically insignificant that were kept anyway because their inclusion scored better scores in our own tests. This likely led to overfitting and would explain why we scored significantly worse on the larger test set.

---
