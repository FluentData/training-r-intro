## Exercises


### Exercise 1

Exercise 1: Plot the relationship between `ws` (wind speed) and `ozone` in the `chicago_air` dataset with `ws` as the x-axis and `ozone` as the y-axis. Make sure to include a title and labels for both axes.

<details><summary>Click for Hint</summary>

Use the `plot()` function in R, providing it with the x and y variables. Include `main` for the title, `xlab` for x-axis label and `ylab` for y-axis label.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
plot(chicago_air$ws, chicago_air$ozone, main='Ozone vs Wind Speed', xlab='Wind Speed', ylab='Ozone')
```
```

#### Output

```r
```r
# R will not produce textual output for a graphical plot.
```
```



</details>

---


### Exercise 2

Exercise 2: Fit a linear regression model to predict `ozone` based on `temp` in the `chicago_air` dataset. Print a summary of the model and interpret the coefficients and the p-value.

<details><summary>Click for Hint</summary>

Use the `lm()` function to fit the linear model. You then obtain the summary of the model using the `summary()` function. From the summary, you can interpret the coefficients and the p-value.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
model <- lm(chicago_air$ozone ~ chicago_air$temp, na.action = na.exclude)
summary(model)
```
```

#### Output

```r
```r
# The output would be dependent on the actual data:
# But in general, it will provide information about the coefficients, residual standard error, etc.
```
```



</details>

---


### Exercise 3

Exercise 3: After fitting the linear model of ozone ~ temp, add the regression line to the scatter plot.

<details><summary>Click for Hint</summary>

First, create a scatter plot for `temp` and `ozone`. Then use `abline()` function to add a line that represents the `model` to this plot.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
plot(chicago_air$temp, chicago_air$ozone, main='Ozone vs Temperature', xlab='Temperature', ylab='Ozone')
abline(model, col='red')
```
```

#### Output

```r
```r
# R will not produce textual output for a graphical plot.
```
```



</details>

---

