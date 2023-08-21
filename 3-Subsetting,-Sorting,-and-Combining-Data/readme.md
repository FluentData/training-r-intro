# Subsetting, Sorting, and Combining Data

To have a sneak-peek into your data, you can harness the power of functions like `head()`, `tail()`, and `View()`.

### head()

The `head()` function shows us the first six rows of the data frame. Use this to get an initial glimpse into the dataset.

```R
# Show first 6 rows of the dataset
head(dataset)
```

### tail()

Similarly, `tail()` gives us the last six rows. This allows you to see the more recent data if your data frame is ordered by time.

```R
# Show last 6 rows of the dataset
tail(dataset)
```

### View()

Lastly, `View()` opens a more user-friendly Data Viewer. This way you can manually scroll through the entire dataset.

```R
# Visualize the dataset
View(dataset)
```

## Table of Contents

1. [Viewing Your Data Frame](#viewing-your-data-frame)
1. [Subsetting Your Data](#subsetting-your-data)
1. [Sorting Data Frames](#sorting-data-frames)
1. [Combining Data Frames](#combining-data-frames)

## Subsetting Your Data

Once you have a handle on what the data looks like, the next course of action is often to select a subset of the data for analysis. We typically do it using `[]`, `$`, and `filter()`.

### Indexing with []

`[]` brackets are a universal way to subset an element from a data structure. To select a particular subset in a data frame, use `[row, column]`.

```R
# Get the ozone value from the 3rd row
dataset[3, "ozone"]
```
### Using $

A handy trick, when you are subsetting a single column, is to use `$`. It is typically used to extract named columns.

```R
# Get all ozone values
dataset$ozone
```

### filter()

The `filter()` function is used to subset rows based on their values. This function is part of the `dplyr` library, which we'll learn more about in upcoming lessons.

```R
# Get rows where ozone is greater than 0.04
filter(dataset, ozone > 0.04)
```

#### Exercise

From the `exam_scores` data frame created in the previous exercise, subset the `math_score` column using both `[]` and `$`. Additionally, use the `filter()` function to return rows where `math_score` is greater than 90.

<details><summary>Click for Hint</summary>

Use `[]` and `$` to subset specific columns from the data frame.

</details>
<details><summary>Click for Hint</summary>

Use `filter()` from `dplyr` package to subset rows based on their values.

</details>
<details><summary>Click for Solution</summary>

#Subset math_score column using []
exam_scores[, 'math_score']

#Subset math_score column using $
exam_scores$math_score

#Filter rows where math_score > 90
filter(exam_scores, math_score > 90)
      
> This exercise reinforces your understanding of subsetting data frames. Using `[]` or `$`, you can extract specific columns, and `filter()` from the `dplyr` package lets you subset rows based on their value.
</details>

---

## Sorting Data Frames

Once you have selected your subset, you might want to order it in a particular sequence. The `arrange()` function helps to do so.

```R
# Sort the dataset by pressure in ascending order
arrange(dataset, pressure)
```

For descending order, use `desc()` function.

```R
# Sort the dataset by temperature in descending order
arrange(dataset, desc(temp))
```

#### Exercise

From the `exam_scores` data frame, sort the data set by `math_score` in ascending order and `english_score` in descending order.

<details><summary>Click for Hint</summary>

Use `arrange()` function from `dplyr` package to sort data frames

</details>
<details><summary>Click for Hint</summary>

For descending order, wrap the column name with `desc()` function inside `arrange()`.

</details>
<details><summary>Click for Solution</summary>

# Sort by math_score in ascending order
arrange(exam_scores, math_score)

# Sort by english_score in descending order
arrange(exam_scores, desc(english_score))
      
> This exercise helps understand the process of sorting data frames using the `arrange()` function. You can sort the data in ascending order by simply passing the column-names as arguments to `arrange()`. To sort in descending order, wrap the column name with `desc()` function.
</details>

---

## Exercises

#### Exercise 1

Create two data frames `students` and `scores` with corresponding student ids. Combine them into a single data frame and arrange it by scores in descending order. Also, filter students who scored more than 80.

<details><summary>Click for Hint</summary>

Use `data.frame()` to create the `students` and `scores` data frames.

</details>
<details><summary>Click for Hint</summary>

Use `bind_rows()` to combine the data frames

</details>
<details><summary>Click for Hint</summary>

Use `arrange()` with `desc()` to sort in descending order.

</details>
<details><summary>Click for Hint</summary>

Use `filter()` to select students who scored more than 80.

</details>
<details><summary>Click for Solution</summary>

students <- data.frame(id = 1:5, name = c('Alice', 'Bob', 'Charlie', 'David', 'Eve'))
scores <- data.frame(id = 1:5, score = c(95, 88, 92, 84, 98))

# Combining data frames
combined <- bind_rows(students, scores)

# Arranging in descending order
combined <- arrange(combined, desc(score))

# Filtering students with score > 80
filter(combined, score > 80)
      
> This problem draws from multiple sections of the lesson including creating data frames, combining them, subsetting based on conditions and arranging them. The solution involves combining `students` and `scores` with matching `id` columns, arranging based on `score` and then filtering students who scored more than 80.
</details>

---

#### Exercise 2

Create two data frames `subjects` and `marks` for five students. Combine them, filter students with `maths` marks more than 90 and arrange in descending order of `science` marks.

<details><summary>Click for Hint</summary>

Use `data.frame()` to create the `students` and `marks` data frames.

</details>
<details><summary>Click for Hint</summary>

Use `bind_rows()` to combine the data frames

</details>
<details><summary>Click for Hint</summary>

Use `filter()` to select students with maths marks more than 90.

</details>
<details><summary>Click for Hint</summary>

Use `arrange()` with `desc()` to sort in descending order of science marks.

</details>
<details><summary>Click for Solution</summary>

students <- data.frame(name = c('Alice', 'Bob', 'Charlie', 'David', 'Eve'))
marks <- data.frame(name = c('Alice', 'Bob', 'Charlie', 'David', 'Eve'), maths = c(95, 88, 92, 84, 98), english = c(87, 91, 84, 92, 85), science = c(89, 85, 95, 88, 96))

# Combining data frames
combined <- bind_rows(students, marks)

# Filtering students with maths > 90
above_90_math <- filter(combined, maths > 90)

# Arranging in descending order of science
arrange(above_90_math, desc(science))
      
> This problem draws from multiple sections of the lesson including creating data frames, combining them, subsetting based on conditions and arranging in a particular order. The solution involves combining `students` and `marks` data frames, filtering students with maths marks more than 90 and then arranging them according to science marks in descending order.
</details>

---

#### Exercise 3

Create a data frame `grades` with the columns `student_Name`, `Math`, `English`, `Science`. View the first and last 3 rows, order it by `Math` in descending order and by `English` in ascending order. Get the values of `Science` column.

<details><summary>Click for Hint</summary>

Use `data.frame()` to create the `grades` data frame.

</details>
<details><summary>Click for Hint</summary>

Use `head()` and `tail()` to view the first and last 3 rows.

</details>
<details><summary>Click for Hint</summary>

Use `arrange()` with `desc()` for descending order and the column-name for ascending order.

</details>
<details><summary>Click for Hint</summary>

To get specific column values, use `grades$<column-name>`.

</details>
<details><summary>Click for Solution</summary>

grades <- data.frame(student_Name = c('Alice', 'Bob', 'Charlie', 'David', 'Eve'), Math = c(95, 88, 92, 84, 98), English = c(87, 91, 84, 92, 85), Science = c(89, 85, 95, 88, 96))

# View first and last 3 rows
head(grades, 3)
tail(grades, 3)

#Order by Math in descending order and English in ascending order
arrange(grades, desc(Math), English)

#Get Science column values
grades$Science
      
> This problem combines concepts from multiple sections of the lesson including creating data frames, viewing specific rows, ordering based on columns and obtaining specific column values.
</details>

---

## Combining Data Frames

Finally, you might have similar data frames that you want to combine for an overall analysis. `bind_rows()` function lets you do just that.

```R
# Combine two similar datasets
bind_rows(dataset1, dataset2)
```
In this session, we learned to index, subset, sort and combine data frames. These techniques can help you immensely in extracting information needed to carry out your analysis in R. Be sure to practice selecting, ordering, and joining datasets to get a good grip on these concepts.

**Up Next:** Our next session, [Writing Functions, Conditionals, and Loops](../4-Writing-Functions-Conditionals-and-Loops/readme.tmd), becomes more exciting as we will learn how to automate data tasks by writing reusable functions, conditional logic and loops.

#### Exercise

Create another data frame `exam_scores2` with similar columns as `exam_scores` but different data. Combine `exam_scores` and `exam_scores2` using the `bind_rows()` function.

<details><summary>Click for Hint</summary>

Create `exam_scores2` using `data.frame()` similar to the first exercise.

</details>
<details><summary>Click for Hint</summary>

Use `bind_rows()` function from `dplyr` package to combine similar data frames.

</details>
<details><summary>Click for Solution</summary>

exam_scores2 <- data.frame(name = c('Frank', 'Grace', 'Harry'), math_score = c(90, 85, 88), english_score = c(84, 89, 90), science_score = c(86, 80, 92))

# Combine exam_scores and exam_scores2
bind_rows(exam_scores, exam_scores2)
      
> This exercise showcases your skill in combining similar data frames using the `bind_rows()` function. This function is beneficial when you have data about the same variables spread across different data frames and want to analyze them together.
</details>

---

