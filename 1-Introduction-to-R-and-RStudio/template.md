# Introduction to R and RStudio

Welcome to the first lesson of the "Introduction to R for Air Quality Data Science" course! In this lesson, we will get started with R and RStudio by learning how to run basic commands, assign variables, and work with data structures. By the end of this lesson, you will have a good understanding of R's core concepts such as variables, data types, vectors, lists, matrices, and data frames.

## Installation and Setup

Before we dive into the world of R, we need to install both R and RStudio on our machine. R is the programming language, and RStudio is the Integrated Development Environment (IDE) that makes writing and running R code easier.

To install R, go to the [R project website](https://www.r-project.org/) and follow the download instructions for your operating system. Once R is installed, you can proceed to install RStudio.

To install RStudio, go to the [RStudio website](https://www.rstudio.com/products/rstudio/download/) and download the free version of RStudio Desktop. Choose the appropriate installer for your operating system and run it to install RStudio.

Now that both R and RStudio are installed, we are ready to begin!

## Getting Started with R

### The R Console

When you open RStudio, you will see a window with several panels. The left panel is the **Console**, where you can interact with R by typing commands and getting immediate results. The console is where we will write and execute R code throughout this course.

To run a command, simply type it in the console and press Enter. For example, if you type `1 + 2` and press Enter, R will evaluate the expression and return the result:

```R
> 1 + 2
[1] 3
```

### Variables and Assignment

In R, we use variables to store and manipulate data. A variable is a name that represents a value or an object in R. We can assign a value to a variable using the assignment operator (`<-` or `=`). Let's see some examples:

```R
# Assigning a value to a variable
x <- 10
y <- 5

# Performing calculations and assigning the result to a variable
sum <- x + y
difference <- x - y
product <- x * y
quotient <- x / y
```

### Basic Data Types

R has several basic data types, including numeric, character, logical, and more. Here are some examples:

```R
# Numeric data type
age <- 30
height <- 175.5

# Character data type
name <- "John Doe"
city <- "Chicago"

# Logical data type
is_student <- TRUE
has_car <- FALSE
```

### Vectors

A vector is a collection of elements of the same data type. We can create a vector using the `c()` function. Here's an example:

```R
# Creating a numeric vector
numbers <- c(1, 2, 3, 4, 5)

# Creating a character vector
fruits <- c("apple", "banana", "orange")
```

We can perform operations on vectors, such as addition, subtraction, and more. The operations will be applied element-wise. Here's an example:

```R
# Adding two numeric vectors
v1 <- c(1, 2, 3)
v2 <- c(4, 5, 6)
result <- v1 + v2
```

### Lists, Matrices, and Data Frames

In addition to vectors, R also provides other data structures like lists, matrices, and data frames.

- Lists: A list is an ordered collection of elements of different data types. We can create a list using the `list()` function.
- Matrices: A matrix is a two-dimensional data structure with rows and columns. We can create a matrix using the `matrix()` function.
- Data Frames: A data frame is a two-dimensional data structure similar to a matrix, but each column can have a different data type. We often use data frames to store and manipulate tabular data. We can create a data frame using the `data.frame()` function.

```R
# Creating a list
person <- list(name = "John Doe", age = 30, city = "Chicago")

# Creating a matrix
matrix1 <- matrix(1:6, nrow = 2, ncol = 3)

# Creating a data frame
data <- data.frame(name = c("John", "Jane", "David"), age = c(30, 25, 35))
```

## Summary

In this lesson, we learned how to get started with R and RStudio. We covered the basics of R programming, including running commands in the R console, assigning variables, and working with data types such as numeric, character, and logical. We also explored vectors as a way to store collections of data, and introduced other data structures like lists, matrices, and data frames.

Now that you have a good understanding of the fundamentals, you are ready to dive deeper into R programming with the next lesson: "Functions and Data Import." In that lesson, you will learn how to use functions in R and import data from common sources. See you there!

## Up Next

In the next lesson, "Functions and Data Import," we will explore how to use functions in R and import data from common sources like CSVs and Excel. You will learn about the core concepts of functions and how to use built-in R functions. We will also cover installing and loading R packages, and importing data into R. Get ready to unlock even more of R's power and flexibility in the next lesson!
