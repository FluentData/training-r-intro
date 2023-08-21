## Functions and Data Import

In this lesson, we will learn how to use functions in R and import data from common sources like CSVs and Excel.

### Objectives

By the end of this lesson, you will be able to:

- Understand what functions are and how to use them
- Use built-in R functions like mean(), paste(), seq()
- Install and load R packages
- Import CSV and Excel data into R

### Functions in R

Functions in R are blocks of reusable code that perform a specific task. They take inputs (arguments) and produce outputs. R has many built-in functions that we can use, and we can also create our own functions.

To use a function, we need to know its name and any required arguments. Arguments are the values or variables that are passed into the function to perform its task. Functions can have zero or more arguments.

Let's start by using some common built-in functions in R.

#### mean()

The `mean()` function calculates the average of a set of numbers. It takes a vector of numbers as its argument and returns the mean value. 

Here's an example:

```R
# Calculate the mean of a vector
numbers <- c(10, 20, 30, 40, 50)
average <- mean(numbers)
print(average)
```

Output:
```
[1] 30
```

#### paste()

The `paste()` function concatenates multiple strings together. It takes any number of arguments and returns a single string.

Here's an example:

```R
# Concatenate multiple strings
name <- "John"
age <- 25
greeting <- paste("Hello,", name, ". You are", age, "years old.")
print(greeting)
```

Output:
```
[1] "Hello, John . You are 25 years old."
```

#### seq()

The `seq()` function generates a sequence of numbers. It takes three arguments: the starting value, the ending value, and the step size. It returns a vector containing the generated sequence.

Here's an example:

```R
# Generate a sequence of numbers
sequence <- seq(1, 10, 2)
print(sequence)
```

Output:
```
[1] 1 3 5 7 9
```

### Packages in R

R packages are collections of functions, data, and documentation that extend the capabilities of base R. There are thousands of packages available for various purposes.

To use a package, we first need to install it. We can use the `install.packages()` function to install packages from the Comprehensive R Archive Network (CRAN), which is the primary repository for R packages.

Here's an example:

```R
# Install the dplyr package
install.packages("dplyr")
```

After installing a package, we need to load it into our R session using the `library()` function.

```R
# Load the dplyr package
library(dplyr)
```

Now we can use the functions provided by the package.

### Importing Data

R can import data from various sources, including CSV files and Excel spreadsheets.

#### CSV Files

To import data from a CSV file, we can use the `read.csv()` function. It takes the file path as its argument and returns a data frame containing the data.

Here's an example:

```R
# Import data from a CSV file
data <- read.csv("path/to/file.csv")
```

Make sure to replace `"path/to/file.csv"` with the actual file path of your CSV file.

#### Excel Spreadsheets

To import data from an Excel spreadsheet, we need to first install and load the `readxl` package. This package provides the `read_excel()` function for importing data from Excel files.

Here's an example:

```R
# Install and load the readxl package
install.packages("readxl")
library(readxl)

# Import data from an Excel file
data <- read_excel("path/to/file.xlsx")
```

Make sure to replace `"path/to/file.xlsx"` with the actual file path of your Excel file.

### Summary

In this lesson, we learned about functions in R and how to use them. We explored some common built-in functions like `mean()`, `paste()`, and `seq()`. We also learned about packages in R, how to install and load them, and how to use functions provided by packages. Finally, we learned how to import data from CSV files using the `read.csv()` function and from Excel spreadsheets using the `read_excel()` function from the `readxl` package.

Now that you have learned about functions and data import in R, you can apply this knowledge to perform a wide range of data analysis tasks. In the next lesson, we will explore subsetting, sorting, and combining data in R.

### Up Next

In the next lesson, we will learn about subsetting, sorting, and combining data in R. [Click here to go to Lesson 3 - Subsetting, Sorting, and Combining Data](./3-Subsetting-Sorting-and-Combining-Data/README.md).