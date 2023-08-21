# Functions and Data Import

After learning about the basics of R and RStudio in the [previous lesson](./1-Introduction-to-R-and-RStudio/readme.tmd), it's time to explore some of the R's built-in functions and understand how to import data into R, specifically from CSVs and Excel files. These are fundamental skills any data scientist working in R will need.

## Table of Contents

1. [What are Functions in R?](#what-are-functions-in-r-)
1. [Importing Data](#importing-data)
1. [Conclusion](#conclusion)
1. [Additional Resources](#additional-resources)
1. [What's Next](#what-s-next)

## What are Functions in R?

In R, a function is a piece of code that is used to perform a specific task. You can think of it as a machine that takes in inputs (called arguments), does something with them, and then gives back some output. Functions can simplify your code by allowing you to re-use the same code without having to write it out every time.

### R's Built-in Functions

R comes with a wide range of built-in functions. Let's look at a few of them:

**mean()** function to calculate the average of a vector:

```R
numbers <- c(5,10,15,20)
mean(numbers)
```

**paste()** function to concatenate strings:

```R
paste("Hello,", "world!")
```

**seq()** function to generate a sequence of numbers:

```R
seq(from = 1, to = 10, by = 2)  # generates 1, 3, 5, 7, 9
```

### Nesting Functions

You can place functions inside other functions, in which case the inner function(s) execute first. For example, you might want to calculate the average temperature for a particular month. To do this, you could first use the `subset()` function to extract the temperature data for that month, and then use the `mean()` function to calculate the average:

```R
# make sure to load the dataset "chicago_air.csv" before using this code
chicago_air <- read.csv("../data/chicago_aqs.csv")

mean(subset(chicago_air, month == 6)$temp)
```

#### Exercise

Create a vector containing numbers 1 to 10 using R. Calculate the mean of this vector using the mean() function.

<details><summary>Click for Hint</summary>

Use `:` for generating sequence of numbers.

</details>
<details><summary>Click for Hint</summary>

Apply the `mean()` function on the created vector to calculate the mean.

</details>
<details><summary>Click for Solution</summary>

numbers <- c(1:10)
mean(numbers)
      
> In R, `c(1:10)` generates a vector of numbers from 1 to 10. The `mean()` function calculates the average of the elements in the vector.
</details>

---

## Importing Data

R's true power comes from its ability to analyze data. But before we can analyze data, we need to import it into R. In this section, we'll look at how to import CSV and Excel files into R.

### CSV

A common data format is the comma-separated values (CSV) file, which can be read into R using the `read.csv()` function. The function needs to know the path of the CSV file you wish to load. 

```R
# Here we assume that the chicago_air.csv file is located in a`data` folder at the same level as this folder.
chicago_air <- read.csv("../data/chicago_air.csv")
```


### Excel

For reading Excel files, we can use libraries like `readxl`.

```R
# Before we can use 'readxl', we need to install and load it using the install.packages and library commands
# Uncomment the lines below to install and load the readxl library
# install.packages("readxl")
# library(readxl)

# Then we can use the read_excel function from the readxl library to read the file.
# chicago_air_excel <- read_excel("../data/chicago_air.xlsx")
```

#### Exercise

Assume we have a CSV file named `data.csv` in a `data` folder. Write a R command to import data from this file.

<details><summary>Click for Hint</summary>

Use the `read.csv()` function to read the CSV file.

</details>
<details><summary>Click for Hint</summary>

The file path should be passed as a string to the `read.csv()` function.

</details>
<details><summary>Click for Solution</summary>

data <- read.csv("../data/data.csv")
      
> In R, the `read.csv()` function is used to read a CSV file and store the data as a dataframe in R.
</details>

---

## Conclusion

Congrats on getting through your first R functions and learning some basics about data import! These skills will be key foundations as we dive deeper into using R for air quality data science.

## Additional Resources

1. [An Introduction to R Functions](https://bookdown.org/learnr/bookdown/more-on-functions.html)
2. [Data Import in R](https://bookdown.org/learnr/bookdown/data-import.html)

## Exercises

#### Exercise 1

Generate a sequence of even numbers from 2 to 20. Calculate the mean of the subset of numbers that are less than 10. Use functions in R.

<details><summary>Click for Hint</summary>

Use `seq()` function to generate a sequence of even numbers.

</details>
<details><summary>Click for Hint</summary>

Use `subset()` function to obtain numbers that are less than 10.

</details>
<details><summary>Click for Hint</summary>

Calculate the mean of the subset numbers using `mean()`.

</details>
<details><summary>Click for Solution</summary>

numbers <- seq(from = 2, to = 20, by = 2)
mean(subset(numbers, numbers < 10))
      
> The `seq()` function is used to generate a sequence of even numbers from 2 to 20. `subset()` is then used to select numbers less than 10 from this sequence. Finally, `mean()` is used to calculate the average.
</details>

---

#### Exercise 2

Concatenate two strings "Hello" and "world" using built-in R functions.

<details><summary>Click for Hint</summary>

Use `paste()` function to concatenate strings.

</details>
<details><summary>Click for Solution</summary>

paste("Hello", ", world!")
      
> The `paste()` function in R concatenates (joins) two or more character strings.
</details>

---

#### Exercise 3

Create a sequence of numbers from 10 to 100, with increment of 10. Calculate the mean and round it off to the nearest integer.

<details><summary>Click for Hint</summary>

Use `seq()` function to generate the sequence.

</details>
<details><summary>Click for Hint</summary>

Use `mean()` function to calculate the mean.

</details>
<details><summary>Click for Hint</summary>

Use `round()` function to round off the value to the nearest whole number.

</details>
<details><summary>Click for Solution</summary>

numbers <- seq(from = 10, to = 100, by = 10)
round(mean(numbers))
      
> The `seq()` function generates a sequence of numbers. The `mean()` function calculates the mean of these numbers. The `round()` function then rounds off the calculated mean to the nearest integer.
</details>

---

#### Exercise 4

Assume that we have an Excel file named `excel_data.xlsx` in the same `data` folder. Write an R command to import data from this file.

<details><summary>Click for Hint</summary>

You must load the `readxl` library using `library()` function.

</details>
<details><summary>Click for Hint</summary>

The `read_excel()` function from `readxl` library can be used to read Excel files.

</details>
<details><summary>Click for Solution</summary>

library(readxl)
excel_data <- read_excel("../data/excel_data.xlsx")
      
> The `read_excel()` function from the `readxl` library in R is used to read Excel files and store the data in R.
</details>

---

## What's Next

Now that we have some data in our R environment, we can learn how to select, order, and join this data in the [next lesson](./3-Subsetting-Sorting-and-Combining-Data/readme.tmd).

