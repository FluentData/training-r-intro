## Exercises


### Exercise 1

Exercise 1: Load the `chicago_air` dataset from the `region5air` package. Display the first 10 rows of the dataset and count the number of rows with temperature greater than 25.

<details><summary>Click for Hint</summary>

Use the `head()` function to display the first 10 rows. To count the rows with temperature greater than 25, use the comparison operator `>` in combination with the `sum()` function.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Load the data
library(region5air)
data(chicago_air)

# Display the first 10 rows
head(chicago_air, 10)

# Count the rows with temperature greater than 25
temp_gt_25 <- sum(chicago_air$temp > 25)
temp_gt_25
```
```

#### Output

```r
```r
# Output will depend on the dataset.
```
```



</details>

---


### Exercise 2

Exercise 2: From the same `chicago_air` dataset, find all rows where the ozone level is greater than 0.040. How many such instances are there?

<details><summary>Click for Hint</summary>

Use the `subset()` function to filter the rows based on the condition. Use `nrow()` to count the number of such rows.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Find rows with ozone > 0.040
high_ozone <- subset(chicago_air, ozone > 0.040)

# Count the number of such instances
nrow(high_ozone)
```
```

#### Output

```r
```r
# Output will depend on the dataset.
```
```



</details>

---


### Exercise 3

Exercise 3: Sort the `chicago_air` dataset by the `temp` column in descending order. Display the top 3 rows of the sorted data.

<details><summary>Click for Hint</summary>

Use the `order()` function to get the order of the rows for sorting. Define the `decreasing` parameter of the `order()` function as `TRUE` for descending order. Use this order in the data frame subsetting.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Sort by temp
sorted_data <- chicago_air[order(chicago_air$temp, decreasing = TRUE), ]

# Display top 3 rows
head(sorted_data, 3)
```
```

#### Output

```r
```r
# Output will depend on the dataset.
```
```



</details>

---

