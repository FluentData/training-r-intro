## Exercises


### Exercise 1

Exercise 1: After loading the 'chicago_air' data, use str() function to understand the structure of the dataset.

<details><summary>Click for Hint</summary>

Use the 'str()' function on the dataset to understand its structure.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
library(region5air)
data(chicago_air)

# Viewing the structure of the dataset
str(chicago_air)
```
```

#### Output

```r
```r
# Output depends on the dataset
```
```



</details>

---


### Exercise 2

Exercise 2: Use the 'boxplot()' function to observe the distribution of the 'ozone' variable in the 'chicago_air' dataset.

<details><summary>Click for Hint</summary>

Use the 'boxplot()' function on the 'ozone' column in the 'chicago_air' dataset. You can include `main` and `ylab` arguments to provide a title and y-label to your plot.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Creating a boxplot of ozone concentrations
boxplot(chicago_air$ozone, main='Boxplot of Ozone Concentrations', ylab='Ozone Concentrations')
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


### Exercise 3

Exercise 3: Use the 'na.locf()' function from the 'zoo' package to replace missing (NA) values of the 'ozone' variable with the previous non-missing value.

<details><summary>Click for Hint</summary>

To use the 'na.locf()' function you will first need to load the 'zoo' package.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
library(zoo)

# Replace NA values with last observation
chicago_air$ozone <- na.locf(chicago_air$ozone, na.rm=FALSE)
```
```

#### Output

```r
```r
# No specific output, the NA values in the 'ozone' column of the dataset are replaced with the previous non-NA value.
```
```



</details>

---

