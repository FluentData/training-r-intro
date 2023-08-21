# Data Transformation and Regression

Data transformations are a ubiquitous method in statistical analysis including air quality data. They help to stabilize variance, make the data more closely align with the assumptions of the inferential model, and improve interpretability. 

### Log, Square root & Box-Cox

For measurements that are skewed, we may apply transformations to reexpress our data for improved analysis. For instance, air pollutant data is often skewed right because it cannot go below zero, but there can be some very high values during pollution events.

Let's import our air quality data and try out some transformations.
  
```R
# Import the data
data <- read.csv("./data/chicago_air.csv")

# Apply a square root transformation
data$sqrt_ozone <- sqrt(data$ozone)

# Apply a log transformation
data$log_ozone <- log(data$ozone)

# Use the boxcox() function to do a Box-Cox transformation
library(MASS)  # boxcox() is in MASS package
data$bc_ozone <- boxcox(data$ozone ~ 1, lambda = seq(-0.5, 0.5, by=0.1))
``` 

The log, square root and Box-Cox are common transformations when dealing with skewed data. Note that Box-Cox is a family of transformations and requires us to choose a 'lambda' parameter that determines the specific transformation to apply.

## Table of Contents

1. [Data Transformations ](#data-transformations-)
1. [Regression Analysis ](#regression-analysis-)
1. [Missing Data ](#missing-data-)
1. [Outliers ](#outliers-)
1. [Wrapping up](#wrapping-up)

## Regression Analysis

We've previously built a simple linear model. It's now time to take it up a notch and bring our new skills together. 

### Simple Linear Regression Model 

Just to refresh, here's how you would build a simple linear model of the relationship of temperature with the ozone.

```R
# Fit the model
model <- lm(ozone ~ temp, data = data)

# Model summary
summary(model)
```

This tells us if there's a statistically significant linear relationship between temperature and ground level ozone concentration. 

### Confidence Intervals 

While summarizing the model will give us coefficient estimates, we can also compute their confidence intervals using the `confint()` function.

```R
# Confidence intervals for model coefficients
confint(model)
```

#### Exercise

Build a simple linear regression model using the 'temp' and the log transformed 'ozone' values. What does the summary of this model tell you?

<details><summary>Click for Hint</summary>

Use the lm() function to create a linear model.

</details>
<details><summary>Click for Hint</summary>

Use the summary() function to provide a summary of the regression model.

</details>
<details><summary>Click for Solution</summary>

model <- lm(log_ozone ~ temp, data = data) 
 summary(model)
      
> The solution fits a simple linear regression model using temperature as the predictor and the log transformed ozone as the response. The summary provides information about the model fit and the significance of the predictors.
</details>

---

## Missing Data

Real-world air quality data often contains missing values, referred to as NAs in R. Before doing many operations in R, we usually need to handle these.

### Handling Missing Values 

```R
# Total number of NAs in dataset
sum(is.na(data$ozone))

# Remove rows with NA values
data <- na.omit(data)

# Check if NAs are removed
sum(is.na(data$ozone))
```

#### Exercise

How many missing values (NAs) are there in the 'ozone' variable and the 'pm25' variable. Remove these rows from the data set.

<details><summary>Click for Hint</summary>

Use the is.na() function to identify missing values.

</details>
<details><summary>Click for Hint</summary>

Use the sum() function to count the total number of NAs.

</details>
<details><summary>Click for Hint</summary>

Use the na.omit() function to remove rows with NA values.

</details>
<details><summary>Click for Solution</summary>

sum(is.na(data$ozone)) 
 sum(is.na(data$pm25)) 
 data <- na.omit(data)
      
> The solution first identifies and counts the number of missing values in 'ozone' and 'pm25'. Then it removes the rows with any NA values from the dataframe.
</details>

---

## Outliers

Finally, let's discuss outliers in our data. Outliers can greatly affect our analysis, especially models because they can lead to erroneous conclusions. 

### Identifying and Handling Outliers

Let's use boxplots to identify potential outliers in our dataset. Boxplots represent the median (middle line), first and third quartiles (box), and the range (whiskers). Outliers are shown as individual points outside the whiskers.

```R
# Create a boxplot
boxplot(data$ozone, main = "Boxplot of Ozone levels", ylab = "Ozone (ppm)", col = "blue")
```
If outliers are found, you could consider removing them, winsorizing the data (replacing outliers with less extreme values), or use robust statistical methods designed to be not too badly affected by outliers.

#### Exercise

Identify potential outliers in the 'temp' variable using a boxplot. Discuss how these can be handled.

<details><summary>Click for Hint</summary>

Use the boxplot() function to create a boxplot.

</details>
<details><summary>Click for Hint</summary>

Outliers are shown as individual points outside the whiskers in a boxplot.

</details>
<details><summary>Click for Solution</summary>

boxplot(data$temp, main = "Boxplot of Temperature", ylab = "Temperature (F)", col = "blue")
      
> The solution creates a boxplot of the 'temp' measurements to visually identify potential outliers. Outliers can be handled by removal, winsorizing, or using robust statistical methods.
</details>

---

## Exercises

#### Exercise 1

Calculate the mean and median of the original 'ozone', and the square root, log, and Box-Cox transformed 'ozone' values. How do these changes with each transformation?

<details><summary>Click for Hint</summary>

Use the mean() and median() functions to calculate respective values.

</details>
<details><summary>Click for Hint</summary>

Note that after transformation, the mean and median values of the data should become closer.

</details>
<details><summary>Click for Solution</summary>

mean_ozone <- mean(data$ozone) 
 median_ozone <- median(data$ozone) 
 mean_sqrt_ozone <- mean(data$sqrt_ozone) 
 median_sqrt_ozone <- median(data$sqrt_ozone) 
 mean_log_ozone <- mean(data$log_ozone) 
 median_log_ozone <- median(data$log_ozone) 
 mean_bc_ozone <- mean(data$bc_ozone) 
 median_bc_ozone <- median(data$bc_ozone)
      
> The solution calculates the mean and median of both the original and transformed 'ozone' data. Comparing these values gives you an insight how transformation affects the distribution of the data.
</details>

---

#### Exercise 2

Build a multiple linear regression model where the dependent variable is the Box-Cox transformed value of 'ozone', and the independent variables are 'temp' and 'pm25'. Summarize this model.

<details><summary>Click for Hint</summary>

Use the lm() function to create a linear model.

</details>
<details><summary>Click for Hint</summary>

Use the + sign to include more than one predictor (independent variable) in the model.

</details>
<details><summary>Click for Hint</summary>

Use the summary() function to summarize the model.

</details>
<details><summary>Click for Solution</summary>

model <- lm(bc_ozone ~ temp + pm25, data = data) 
 summary(model)
      
> The solution fits a multiple linear regression model using temperature and 'pm25' as predictors and the Box-Cox transformed ozone as the response. The summary provides information about the model fit and the significance of the predictors.
</details>

---

#### Exercise 3

Create a new variable 'bad_air_day' that is 'yes' if the ozone level is greater than its median and 'no' otherwise. How many 'bad air days' are there in the dataset?

<details><summary>Click for Hint</summary>

Use the ifelse() function to create a new variable based on a condition.

</details>
<details><summary>Click for Hint</summary>

Use the table() function to count the number of 'bad air days'.

</details>
<details><summary>Click for Solution</summary>

data$bad_air_day <- ifelse(data$ozone > median(data$ozone), 'yes', 'no') 
 table(data$bad_air_day)
      
> The solution creates a new variable 'bad_air_day' which is 'yes' if the ozone level is greater than its median and 'no' otherwise. Then it counts the number of 'bad air days' using the table() function.
</details>

---

#### Exercise 4

Remove the 'temp' variable from the dataset and then try to fit the same linear model as before. What happened? Why?

<details><summary>Click for Hint</summary>

Use the NULL assignment to remove a column from the dataframe.

</details>
<details><summary>Click for Hint</summary>

The lm() function will return an error if one of the variables in the formula is not found in the dataframe.

</details>
<details><summary>Click for Solution</summary>

data$temp <- NULL 
 model <- lm(bc_ozone ~ temp + pm25, data = data)
      
> The solution removed the 'temp' variable from the dataframe and then tries to fit the regression model that includes 'temp' as a predictor. Since 'temp' no longer exists in the dataframe, an error is returned.
</details>

---

## Wrapping up

In this lesson, we dove deep into the world of data pre-processing before regression analysis, including important topics like data transformations, regression modeling, handling missing data and outliers. All of these make up key steps for accurately interpreting real-world air quality data. 

**[Up Next](../8-quality-assurance/readme.tmd)**: As we near the end of this introductory R course, we will look at ensuring the quality of our data and output. Remember, there will always be garbage-in, garbage-out phenomenon in data science, to get quality output, you need to ensure the quality of the input. Head on over to the next lesson where we will learn techniques to assess and improve data quality!

