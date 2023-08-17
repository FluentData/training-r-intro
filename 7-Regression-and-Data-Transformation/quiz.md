## Quiz


### 1. What is linear regression?

1. A machine learning algorithm for classification problems
1. A method to figure out the relationship between two variables
1. A method to convert categorical variables into dummy variables
1. A type of data preprocessing method in R
<details><summary>Click for Answer</summary>

#### Answer

2.  A method to figure out the relationship between two variables

> Linear regression is a statistical technique that is useful in understanding the relationship between two continuous variables. It can be used to find out which value of the prediction variable will most likely occur when the outcome takes on a certain value.</details>

---


### 2. What does the lm() function in R do?

1. It performs linear regression
1. It calculates correlation between two variables
1. It creates a scatter plot
1. It calculates the mean of a variable
<details><summary>Click for Answer</summary>

#### Answer

1.  It performs linear regression

> The function lm() in R is used to fit linear models, including but not limited to simple and multiple linear regression.</details>

---


### 3. Using the lm() function, what is the correct order of the response and explanatory variables in the formula argument?

1. lm(formula = response variable ~ explanatory variable)
1. lm(formula = explanatory variable ~ response variable)
1. lm(formula = response variable & explanatory variable)
1. lm(formula = explanatory variable & response variable)
<details><summary>Click for Answer</summary>

#### Answer

1.  lm(formula = response variable ~ explanatory variable)

> In the formula argument of the lm() function in R, the response variable comes before the ~ symbol and the explanatory variable(s) comes after. The ~ symbol can be read as 'on' or 'as a function of'.</details>

---


### 4. What do the residuals from a linear model represent?

1. The difference between the observed and predicted values
1. The correlation between the observed and predicted values
1. The average of the observed and predicted values
1. The ratio of the observed to the predicted values
<details><summary>Click for Answer</summary>

#### Answer

1.  The difference between the observed and predicted values

> Residuals represent the difference between the observed value and the predicted value of the response variable. They are used to understand the discrepancy between the model and the data.</details>

---


### 5. In the context of a linear regression model in R, what is the significance of the p-value given by Pr(>|t|)?

1. It tells us the probability that the true coefficient is zero
1. It tells us the probability that the model fits the data perfectly
1. It tells us the correlation between the variables
1. None of the above
<details><summary>Click for Answer</summary>

#### Answer

1.  It tells us the probability that the true coefficient is zero

> The p-value tells us the probability of obtaining a result as extreme as, or more extreme than, the result observed under the null hypothesis of the model. In the context of linear regression, a low p-value (typically considered less than 0.05) indicates that it is unlikely the true coefficient is zero, implying that the corresponding variable is significant in the model.</details>

---

