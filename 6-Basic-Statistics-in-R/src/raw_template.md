# Basic Statistics in R

In the previous [lesson](./5-Plotting-with-ggplot2/readme.tmd), we used ggplot2 to create visualizations of air quality data. With the ability to visualize our data, we'll now learn how to describe the data numerically and perform some basic statistical analyses.

We'll be focusing on descriptive statistics, t-tests, one-way ANOVA, and simple linear regression. You might be familiar with some of these techniques from using Excel, but we'll explore how to perform them in R, where they can be integrated into scripts for automation and reproducibility.

## Descriptive Statistics

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

## T-Tests

The `t.test()` function in R allows us to conduct t-tests, which can be used to test hypotheses about population means.

```r
# one-sample t-test: Is the mean ozone concentration different from 0.035 ppm?
t.test(chicago_air$ozone, mu = 0.035, na.rm = TRUE)
```

Results are returned in a compact form, stating the t-value, degrees of freedom, and p-value among others. 

## One-way ANOVA

Analysis of variance (ANOVA) can be used to test for the equality of three or more means. We can perform a one-way ANOVA with the `aov()` function. 

Let's test whether there's a difference in mean ozone concentration between months.

```r
# One-way ANOVA of ozone with respect to month
anova_model <- aov(ozone ~ month, data = chicago_air)
summary(anova_model)
```

The `summary` function gives us the results including the F-statistic and p-value.

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