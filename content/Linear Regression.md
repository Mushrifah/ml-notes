---
tags:
  - ml
---

- [[#Contents:|Contents:]]
- [[#Linear regression]]
- [[#Ordinary Least Squares (OLS)]]
- [[#Code in Python:|Code in Python:]]



-------------------------------

# Contents:
- Linear Regression introduction
- Gauss markov assumptions
- Types of linear regression -> linear, multiple, ols, ridge, lasso, elasticnet
- Evaluation metrics -> understand all the different components in the results with all stats concepts
- stats concepts -> interaction terms, multicollinearity (vif), R-squared, adjusted R-squared, exogenous and endogenous variables
-  Adv and disadv
- Implementation with python -> statsmodel, sklearn
- Implementation with R


----------------------------

# Linear regression

Simple linear regression will have one dependent variable (Yi) and one independent variable(Xi)
and the equation below represents the linear relationship between the two variables
$Y_i = \beta_{0} + \beta_{1}X_{i}$




goal is to find best fit by squaring the residuals and then minimize the sum of squares.
**εi =**  **ypredicted** –   **yi**
**where** **ypredicted** **=   B0 + B1 Xi**

In this case 


$R^2 = 1 - \frac{\sum(y_{i} - y_{predicted})^2 } {\sum(y_{i} - y_{mean})^2}$










-----------------


# Ordinary Least Squares (OLS):

- parametric method estimating parameters also called coefficients, that describes data relationships

- least squares:- method to find best fit by squaring the residuals and then minimize the sum of squares.

- BLUE -> Best linear unbiased estimator.  
- lower standard errors -> more certainity around the results.

- conditions that make OLS blue are called Gauss Markov Assumptions:-  
    - Linear parameters:- dependent variable must be continuously measured variable.  
    - exogeneity condition:- no correation between explanatory variables and error term (means X is an independent variable and Y depends on X.)  
        - exogenous: explanatory variable(X)  
        - endogenous: correlated with error term  (Y)  
    - homoscedasticity assumption:- variation of noise in the data must remain stable across the explanatory variables.  
    - Collinearity assumption:- explanatory variables should not be highly correlated with each other.

- Model fit metrics:  
    - TSS (Total sum of squares) = (y-y_mean)^2  
    - RSS(residual sum of squares) = Unexplained variation  
    - R-squared :- lies between 0-1  
	    = (TSS-RSS)/TSS   
	    = Explained variation/total variation  
	    = 1 - Unexplained variation/Total variation   
	    = 1 - RSS/TSS  
    - RSS decrease -> regression line was very close to actual points -> independent variable explain majority of variation in the target variable -> R-squared increase   
      
    - Adjusted R-squared :- penalizes the inclusion of unecessary variables -> u can add more predictors to the model and if increase then new variable improves the model performance  
	    = 1 - (1-R^2)(n-1)/(n-k-1)  
	    where R:- R-squared values , n:- no.of data points, k:- no. of independent variables

- regression with quadratic term:- additional squared explanatory variable can lead to a quadartic relationship with dependent variable -> both variables act like a quadratic equation

- Indicator variables:-   
    - these are categorical variables used (but they should be in the form of two categories only ie if 1 or 0 and if it is more than 2 categories then create different columns for each  category and fill it with binary value based on its occurence for each category. )  
    - these variables shift the regression lines up or down  
    - there should be a reference category for it to make sense of the indicator coefficients/variables

- Time can be used as variable in regression model.

- For Elasticities we use log transformations for variables.




---------------

- check Multicollinearity if the Variance Inflation Factor (VIF) value is > 10  
- If the ols model has Multicollinearity problems (large variance -> overfitting) then use lasso or ridge regression.  
- Ridge Regression is best used if the data do not have many predictor variables (penality component squared)  
whereas LASSO Regression is good if the data has many predictor variables (penality component absolute value), because it will simplify the interpretation of the model.


----------------------------------

## Code in Python:

```python
from matplotlib import pyplot as plt
import seaborn as sns
```



-------

## References
- https://www.analyticsvidhya.com/blog/2021/10/everything-you-need-to-know-about-linear-regression/#h-what-is-linear-regression
- https://utsavdesai26.medium.com/linear-regression-made-simple-a-step-by-step-tutorial-fb8e737ea2d9