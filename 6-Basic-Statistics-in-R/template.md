# Basic Statistics in R

In this lesson, we will learn how to perform basic statistical analysis in R. We will cover how to calculate summary statistics such as mean, median, and correlation, as well as how to generate confidence intervals and perform t-tests. Additionally, we will explore how to conduct ANOVA analysis and fit linear models. By the end of this lesson, you will have a solid foundation in using R for basic statistical analysis.

## Descriptive Statistics

Descriptive statistics provide measures that summarize and describe the main features of a dataset. Some commonly used descriptive statistics include measures of central tendency (e.g., mean and median) and measures of spread (e.g., standard deviation and variance). R provides several built-in functions to calculate these statistics.

### Mean and Median

The mean and median are both measures of central tendency. The mean is the average of all the values in a dataset, while the median is the middle value when the dataset is sorted in ascending order. To calculate the mean and median in R, we can use the `mean()` and `median()` functions, respectively.

Let's calculate the mean and median of a variable in the `chicago_air` dataset:

```R
# Calculate the mean and median of the ozone variable
mean_ozone <- mean(chicago_air$ozone)
median_ozone <- median(chicago_air$ozone)

mean_ozone
median_ozone
```

The `mean_ozone` variable will store the mean of the ozone variable, and the `median_ozone` variable will store the median.

### Standard Deviation and Variance

The standard deviation and variance are measures of spread. The standard deviation measures the average amount by which data points deviate from the mean, while the variance is the average of the squared deviations from the mean. In R, we can use the `sd()` and `var()` functions to calculate the standard deviation and variance, respectively.

Let's calculate the standard deviation and variance of the temperature variable in the `chicago_air` dataset:

```R
# Calculate the standard deviation and variance of the temperature variable
sd_temp <- sd(chicago_air$temp)
var_temp <- var(chicago_air$temp)

sd_temp
var_temp
```

The `sd_temp` variable will store the standard deviation of the temperature variable, and the `var_temp` variable will store the variance.

### Correlation

Correlation measures the strength and direction of the linear relationship between two variables. It takes values between -1 and 1, where -1 indicates a perfect negative correlation, 1 indicates a perfect positive correlation, and 0 indicates no correlation. In R, we can use the `cor()` function to calculate the correlation coefficient.

Let's calculate the correlation between the ozone and temperature variables in the `chicago_air` dataset:

```R
# Calculate the correlation coefficient between ozone and temperature
correlation <- cor(chicago_air$ozone, chicago_air$temp)

correlation
```

The `correlation` variable will store the correlation coefficient between the ozone and temperature variables.

## Confidence Intervals and Inference

Confidence intervals provide a range of plausible values for a population parameter, such as a population mean or a population proportion. They are used to estimate the precision of our sample estimate and provide a measure of uncertainty. R provides functions to calculate confidence intervals for means, proportions, and other parameters.

### t-tests and Confidence Intervals for Means

A t-test is a statistical test used to determine whether there is a significant difference between the means of two groups. It can also be used to calculate confidence intervals for means. In R, we can use the `t.test()` function to perform a t-test and generate confidence intervals for means.

Let's perform a t-test and calculate a confidence interval for the mean ozone concentration in the `chicago_air` dataset:

```R
# Perform a one-sample t-test for the mean ozone concentration
t_test <- t.test(chicago_air$ozone)

# Calculate the confidence interval
conf_interval <- t_test$conf.int

conf_interval
```

The `conf_interval` variable will store the confidence interval for the mean ozone concentration.

### ANOVA Analysis

ANOVA (Analysis of Variance) is a statistical technique used to compare the means of three or more groups. It determines whether there are any statistically significant differences among the means and provides an overall measure of variability. In R, we can use the `aov()` function to perform ANOVA analysis.

Let's perform an ANOVA analysis on the ozone concentrations grouped by month in the `chicago_air` dataset:

```R
# Perform ANOVA analysis on ozone concentrations by month
anova_result <- aov(ozone ~ month, data = chicago_air)

summary(anova_result)
```

The `anova_result` variable will store the ANOVA analysis result, and the `summary()` function will provide an overview of the analysis.

## Linear Models

Linear regression is a statistical technique used to model the relationship between a dependent variable and one or more independent variables. It allows us to predict the value of the dependent variable based on the values of the independent variables. In R, we can use the `lm()` function to fit linear regression models.

Let's fit a simple linear regression model to the data, with ozone as the dependent variable and temperature as the independent variable, using the `chicago_air` dataset:

```R
# Fit a linear regression model
lm_model <- lm(ozone ~ temp, data = chicago_air)

# View the summary of the model
summary(lm_model)
```

The `lm_model` variable will store the linear regression model, and the `summary()` function will provide an overview of the model.

## Summary

In this lesson, we learned how to perform basic statistical analysis in R. We covered calculating summary statistics such as mean, median, standard deviation, variance, and correlation. We also explored generating confidence intervals and performing t-tests, ANOVA analysis, and linear regression. By utilizing these techniques, you can gain valuable insights from your data and make informed decisions based on statistical evidence.

## Up Next

In the next lesson, we will dive into data transformation and regression in R. We will learn how to transform variables using standard transformations, perform basic regression analysis and inference, and handle missing data and outliers. Let's continue our journey of using R for air quality data analysis!