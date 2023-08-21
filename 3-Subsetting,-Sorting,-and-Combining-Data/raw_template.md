# Subsetting, Sorting, and Combining Data

As we venture deeper into R, it becomes essential to know how to examine, slice and dice the data to satisfy our analytical needs. In the [previous lesson](../2-Functions-and-Data-Import/readme.tmd), we learned how to import data and use functions. Now, we will delve into how to subset data frames, arrange the data in a particular source and combine multiple data frames.

## Viewing Your Data Frame

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

## Combining Data Frames

Finally, you might have similar data frames that you want to combine for an overall analysis. `bind_rows()` function lets you do just that.

```R
# Combine two similar datasets
bind_rows(dataset1, dataset2)
```
In this session, we learned to index, subset, sort and combine data frames. These techniques can help you immensely in extracting information needed to carry out your analysis in R. Be sure to practice selecting, ordering, and joining datasets to get a good grip on these concepts.

**Up Next:** Our next session, [Writing Functions, Conditionals, and Loops](../4-Writing-Functions-Conditionals-and-Loops/readme.tmd), becomes more exciting as we will learn how to automate data tasks by writing reusable functions, conditional logic and loops.