# Functions and Data Import

## Introduction

After learning about the basics of R and RStudio in the [previous lesson](./1-Introduction-to-R-and-RStudio/readme.tmd), it's time to explore some of the R's built-in functions and understand how to import data into R, specifically from CSVs and Excel files. These are fundamental skills any data scientist working in R will need.

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

## Conclusion

Congrats on getting through your first R functions and learning some basics about data import! These skills will be key foundations as we dive deeper into using R for air quality data science.

## Additional Resources

1. [An Introduction to R Functions](https://bookdown.org/learnr/bookdown/more-on-functions.html)
2. [Data Import in R](https://bookdown.org/learnr/bookdown/data-import.html)

## What's Next

Now that we have some data in our R environment, we can learn how to select, order, and join this data in the [next lesson](./3-Subsetting-Sorting-and-Combining-Data/readme.tmd).