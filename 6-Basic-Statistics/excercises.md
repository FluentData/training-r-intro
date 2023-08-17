## Exercises


### Exercise 1

Exercise 1: Compute the minimum, maximum, and range of the 'temp' column from the 'chicago_air' dataset. Remember to handle NA values.

<details><summary>Click for Hint</summary>

Use built-in R functions: `min()`, `max()`, and `range()`. Remember to set `na.rm=True` to ignore NA values.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Minimum
min_temp <- min(chicago_air$temp, na.rm=True)
print(min_temp)

# Maximum
max_temp <- max(chicago_air$temp, na.rm=True)
print(max_temp)

# Range
range_temp <- range(chicago_air$temp, na.rm=True)
print(range_temp)
```
```

#### Output

```r
```r
# The actual output depends on the dataset.
```
```



</details>

---


### Exercise 2

Exercise 2: Calculate the mean, median, variance, and standard deviation of the 'ozone' column of the 'chicago_air' data. Also, remember to handle NA values.

<details><summary>Click for Hint</summary>

Use the built-in R functions: `mean()`, `median()`, `var()`, and `sd()`. Remember to set `na.rm=True` to ignore NA values.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Mean
mean_ozone <- mean(chicago_air$ozone, na.rm=True)
print(mean_ozone)

# Median
median_ozone <- median(chicago_air$ozone, na.rm=True)
print(median_ozone)

# Variance
var_ozone <- var(chicago_air$ozone, na.rm=True)
print(var_ozone)

# Standard Deviation
sd_ozone <- sd(chicago_air$ozone, na.rm=True)
print(sd_ozone)
```
```

#### Output

```r
```r
# The actual output depends on the dataset.
```
```



</details>

---


### Exercise 3

Exercise 3: Perform a t-test to compare the 'ozone' values between March (month == 3) and June (month == 6) in the 'chicago_air' dataset. Interpret the results.

<details><summary>Click for Hint</summary>

Use the `subset()` function to filter the dataset for the specified months. Then use these subsets in the `t.test()` function to compare the ozone levels.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Subset data for March and June
ozone_march <- subset(chicago_air, month == 3)$ozone
ozone_june <- subset(chicago_air, month == 6)$ozone

# T-test
result <- t.test(ozone_march, ozone_june, na.rm=True)
print(result)
```
```

#### Output

```r
```r
# The actual output will depend on the dataset.
```
```



</details>

---

