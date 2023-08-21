# Subsetting, Sorting, and Combining Data

In this lesson, you will learn techniques for selecting, ordering, and joining datasets in R. These skills are essential for working with and manipulating data to extract meaningful insights. Specifically, we will cover subsetting data frames, sorting rows, and combining multiple data frames together.

## Selecting Data Subsets

Before we dive into subsetting, let's start by understanding how to inspect data frames using the `head()`, `tail()`, and `View()` functions. These functions allow you to take a quick look at the beginning or end of a data frame or open it in a separate window for easier exploration.

### Using `head()`, `tail()`, and `View()`

The `head()` and `tail()` functions are useful for inspecting the first or last few rows of a data frame. They can help you get a sense of the structure and contents of a dataset.

```R
# Display the first 6 rows of a data frame
head(dataset)

# Display the last 6 rows of a data frame
tail(dataset)

# Open a separate window to view the entire data frame
View(dataset)
```

Now that you know how to inspect the data, let's move on to subset selection.

### Subsetting with `[ ]`

The simplest way to subset a data frame in R is by using square brackets `[ ]`. You can use `[ ]` to extract specific rows, columns, or subsets of both.

To subset rows, you can use the row indices inside `[ ]`. For example, `data[1, ]` will return the first row of the data frame `data`, and `data[1:5, ]` will return the first five rows.

To subset columns, you can use the column names or indices inside `[ ]`. For example, `data[, "column_name"]` will return the column named "column_name", and `data[, c(1, 3, 5)]` will return the first, third, and fifth columns.

To subset both rows and columns, you can combine the row and column subsetting inside `[ ]`. For example, `data[1:5, c("column1", "column3")]` will return the first five rows of columns "column1" and "column3".

### Subsetting with `$`

Another way to subset a data frame is by using the `$` operator. The `$` operator allows you to directly access columns by their name. For example, `data$column_name` will return the column named "column_name".

The `$` operator is convenient when you want to extract just one column from a data frame. However, it does not allow for subsetting rows.

### Filtering Rows with `filter()`

The `filter()` function from the `dplyr` package provides a more flexible way to subset rows based on specific conditions. To use `filter()`, you need to load the `dplyr` package using the `library()` function.

Here's an example of how to use `filter()` to select rows based on a condition:

```R
library(dplyr)

# Filter the data frame to only include rows where the temperature is above 25 degrees
filtered_data <- filter(data, temperature > 25)
```

In this example, the resulting `filtered_data` data frame will only contain rows where the temperature value is greater than 25.

## Sorting Rows

In addition to subsetting, you may need to sort the rows of a data frame based on a specific variable. The `arrange()` function from the `dplyr` package can help with this.

### Using `arrange()`

To sort a data frame by a specific column, you can use the `arrange()` function. By default, `arrange()` will sort the rows in ascending order of the specified column.

Here's an example of how to use `arrange()` to sort a data frame by the "temperature" column:

```R
library(dplyr)

# Sort the data frame by the temperature column in ascending order
sorted_data <- arrange(data, temperature)
```

In this example, the resulting `sorted_data` data frame will have its rows arranged in ascending order based on the "temperature" column.

To sort in descending order, you can use the `desc()` function. Here's an example:

```R
library(dplyr)

# Sort the data frame by the temperature column in descending order
sorted_data <- arrange(data, desc(temperature))
```

In this example, the resulting `sorted_data` data frame will have its rows arranged in descending order based on the "temperature" column.

## Combining Data Frames

In some situations, you may need to combine multiple data frames together. This can be achieved using the `bind_rows()` function from the `dplyr` package.

### Combining Data Frames with `bind_rows()`

The `bind_rows()` function allows you to stack data frames vertically. It is useful when you have data frames with the same columns and want to merge them into a single data frame.

Here's an example of how to use `bind_rows()` to combine two data frames:

```R
library(dplyr)

# Combine two data frames into a single data frame
combined_data <- bind_rows(data1, data2)
```

In this example, `combined_data` will contain the rows from both `data1` and `data2`, stacked vertically.

If the data frames have different columns, `bind_rows()` will create missing values for columns that do not exist in certain data frames.

## Summary

In this lesson, you learned how to select subsets of data frames using `[ ]` and `$`. You also learned how to filter rows based on specific conditions using the `filter()` function from the `dplyr` package. Additionally, you learned how to sort rows using the `arrange()` function, and how to combine multiple data frames together using the `bind_rows()` function.

Now that you are familiar with subsetting, sorting, and combining data, you can apply these techniques to manipulate and analyze datasets in R.

## Up Next

In the next lesson, we will explore how to write custom functions in R, use conditional logic to control program flow, and automate data tasks using loops. You will gain valuable skills to make your data processing more efficient and scalable. [Next Lesson: Writing Functions, Conditionals, and Loops](./4-Writing-Functions-Conditionals-and-Loops/readme.md)