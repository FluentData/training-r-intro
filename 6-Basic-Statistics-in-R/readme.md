# Basic Statistics in R

To understand our data, we often start by calculating descriptive or summary statistics. 

### Mean and Median

We can use the `mean()` function to calculate average of a numeric vector. For example, to find the mean ozone level in our chicago_air dataset, we run:

```r
mean(chicago_air$ozone, na.rm = TRUE)
```

Note the `na.rm = TRUE` argument, which instructs R to ignore `NA` values when calculating the mean.

The median, or the middle value in a sorted list of numbers, can be calculated using the `median()` function in the same way.

```r
median(chicago_air$ozone, na.rm = TRUE)
```

### Standard Deviation and Variance

To quantify the spread of numeric data, we can compute the standard deviation with the `sd()` function, and the variance with the `var()` function.

```r
# Standard Deviation
sd(chicago_air$ozone, na.rm = TRUE)

# Variance
var(chicago_air$ozone, na.rm = TRUE)
```

### Correlation

To assess the relationship between two numeric variables, we can calculate their correlation using the `cor()` function.

```r
# Correlation between temperature and ozone
cor(chicago_air$temp, chicago_air$ozone, use = "pairwise.complete.obs")
```

The `use = "pairwise.complete.obs"` argument asks R to ignore pairs of values that include at least one `NA`.

## Table of Contents

1. [Descriptive Statistics](#descriptive-statistics)
1. [T-Tests](#t-tests)
1. [One-way ANOVA](#one-way-anova)
1. [Simple Linear Regression](#simple-linear-regression)

## T-Tests

The `t.test()` function in R allows us to conduct t-tests, which can be used to test hypotheses about population means.

```r
# one-sample t-test: Is the mean ozone concentration different from 0.035 ppm?
t.test(chicago_air$ozone, mu = 0.035, na.rm = TRUE)
```

Results are returned in a compact form, stating the t-value, degrees of freedom, and p-value among others.

#### Exercise

Perform a one-sample t-test on the `wind` column of the `chicago_air` dataset with `mu` equal to 10. Ignore `NA` values.

<details><summary>Click for Hint</summary>

Use the `t.test` function in R. Remember to set `mu` and handle `NA` values.

</details>
<details><summary>Click for Solution</summary>

t.test(chicago_air$wind, mu = 10, na.rm = TRUE)
      
> This command performs a one-sample t-test on the `wind` column of the `chicago_air` dataset. Null hypothesis is that the mean wind speed is equal to 10. The p-value < 0.05 suggests that the mean wind speed in the data is significantly different from 10.
</details>

---

## One-way ANOVA

Analysis of variance (ANOVA) can be used to test for the equality of three or more means. We can perform a one-way ANOVA with the `aov()` function. 

Let's test whether there's a difference in mean ozone concentration between months.

```r
# One-way ANOVA of ozone with respect to month
anova_model <- aov(ozone ~ month, data = chicago_air)
summary(anova_model)
```

The `summary` function gives us the results including the F-statistic and p-value.

#### Exercise

Perform a one-way ANOVA using the `chicago_air` dataset to see if `wind` speed varies significantly across different months. Ignore `NA` values.

<details><summary>Click for Hint</summary>

Use the `aov` function for ANOVA analysis and `summary` function to display the results.

</details>
<details><summary>Click for Solution</summary>

anova_model <- aov(wind ~ month, data = chicago_air)
summary(anova_model)
      
> These commands perform a one-way ANOVA to test if there's a difference in average wind speed between different months in the `chicago_air` dataset. The very low p-value suggests that the wind speeds do vary significantly across different months.
</details>

---

## Exercises

#### Exercise 1

Using the `chicago_air` dataset, calculate the mean `ozone` level and perform a t-test to check if it is different from 0.04. Afterwards, fit a linear regression model that predicts `ozone` level from `temp`. Ignore `NA` values.

<details><summary>Click for Hint</summary>

Use the `mean`, `t.test` and `lm` functions while handling `NA` values. Remember to display the summary of the linear regression model.

</details>
<details><summary>Click for Solution</summary>

avg_ozone <- mean(chicago_air$ozone, na.rm = TRUE)
test_result <- t.test(chicago_air$ozone, mu = 0.04, na.rm = TRUE)
lm_model <- lm(ozone ~ temp, data = chicago_air)
list(avg_ozone = avg_ozone, test_result = test_result, lm_model = summary(lm_model))
      
> This command first calculates the mean `ozone` level in the `chicago_air` dataset, then conducts a t-test to check if it's different from 0.04, and finally fits a linear model predicting `ozone` level from `temp`. The p-value from the t-test is larger than 0.05, suggesting that the mean ozone level is not significantly different from 0.04. However, temperature is a significant predictor of ozone level in the linear regression model.
</details>

---

#### Exercise 2

Calculate the correlation between `temp` and `ozone`, and then fit a linear regression model that predicts `ozone` level from `temp`. Use the `chicago_air` dataset and ignore `NA` values.

<details><summary>Click for Hint</summary>

Use the `cor` and `lm` functions in your implementation. Handle `NA` values appropriately and remember to display the summary of the linear regression model.

</details>
<details><summary>Click for Solution</summary>

correl <- cor(chicago_air$temp, chicago_air$ozone, use = 'pairwise.complete.obs')
lm_model <- lm(ozone ~ temp, data = chicago_air)
list(correlation = correl, lm_model = summary(lm_model))
      
> This command first calculates the correlation between `temp` and `ozone` in the `chicago_air` dataset and then fits a linear regression model predicting `ozone` from `temp`. The correlation indicates a fairly strong positive relationship between temperature and ozone levels. The coefficients in the linear regression model also suggest that `temp` is a significant predictor of `ozone`.
</details>

---

#### Exercise 3

Perform a t-test on the `ozone` column with `mu` equal to the mean `ozone` level, and then conduct a one-way ANOVA to test if there is a difference in mean `ozone` level between different months. Use the `chicago_air` dataset and ignore `NA` values.

<details><summary>Click for Hint</summary>

Use the `mean`, `t.test` and `aov` functions in your script. Make sure you handle `NA` values appropriately.

</details>
<details><summary>Click for Solution</summary>

avg_ozone <- mean(chicago_air$ozone, na.rm = TRUE)
test_result <- t.test(chicago_air$ozone, mu = avg_ozone, na.rm = TRUE)
anova_model <- aov(ozone ~ month, data = chicago_air)
list(t_test = test_result, anova = summary(anova_model))
      
> The command first calculates the mean `ozone` level and conducts a t-test to check if the mean `ozone` level differs from the calculated mean - it doesn't. Then it conducts a one-way ANOVA to test if there's a difference in mean `ozone` levels between different months. The p-value from the ANOVA is greater than 0.05, suggesting that the means are not significantly different.
</details>

---

## Simple Linear Regression

Finally, we can build simple linear regression models using the `lm()` function.

Let's fit a model to predict ozone level from temperature:

```r
# Fit a linear model
lm_model <- lm(ozone ~ temp, data = chicago_air)

# Display the model's summary
summary(lm_model)
```

This model's summary provides regression coefficients, standard errors, t-values, and p-values, among other things.

In this lesson, you've learned how to compute basic statistics in R. In the next [lesson](./7-Data-Transformation-and-Simple-Regression/readme.tmd), we'll transform our data and delve deeper into regression analysis.

#### Exercise

Use the `chicago_air` dataset to fit a linear regression model that predicts `wind` speed using `temp` as a predictor. Display the model summary.

<details><summary>Click for Hint</summary>

Use the `lm` function to create a linear model, and `summary` to display the results.

</details>
<details><summary>Click for Solution</summary>

lm_model <- lm(wind ~ temp, data = chicago_air)
summary(lm_model)
      
> These commands fit a linear regression model to the `chicago_air` dataset, using `temp` to predict `wind` speed. The summary indicates that temperature is not a significant predictor of wind speed.
</details>

---

