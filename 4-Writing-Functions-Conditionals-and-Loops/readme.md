

This lesson covers how to write your own R functions. It also explains how to automate
your code using `if()` and `ifelse()` functions, for loops, and the `apply`
function.


- [Prerequisites](#prerequisites)
- [Writing Functions](#writing-functions)
- [if Functions](#if-functions)
- [for Loops](#for-loops)
- [apply Function](#apply-function)
- [Exercises](#exercises)

<br>
<hr>
<br>

# Prerequisites

This lesson assumes you are familiar with the material in the previous lessons:

- [Functions and Importing Data](../2-Functions-and_Importing-Data/readme.md) 
- [Subsetting, Sorting, and Combining Data Frames](../3-Subsetting-Sorting-and-Combining/readme.md).

The data from the R package `region5air` is used throughout these lessons.
To install the package from GitHub, use the `remotes` package. Run the code
below to install the `remotes` package and install `region5air` from GitHub.


```r
# if you have not installed remotes
install.packages("remotes")

library(remotes)
install_github("FluentData/region5air")
```

To load the `chicago_air` data frame we will be using in the lesson, use the 
`library()` function to load the `region5air` package, then the `data( )` function
to load the data frame. 


```r
library(region5air)

data(chicago_air)
```


# Writing Functions

As discussed in the [second lesson on functions](../2-Functions-and-Importing-Data/readme.md),
R can execute a saved chunk of code by running the name of a function, like `mean()`.
The name `mean` is saved like a variable name, but since the name refers to a function,
the thing that's saved is not a data object but lines of R code. 

To save your own function, use this construction:


```r
my_function_name <- function() {
  
  # lines of R code
  
}
```

We can write a simple function that prints something to the console. Here is a
function named `print_hello`.


```r
print_hello <- function() {
  
  print("Hello")
  
}
```

This function can now be executed like any other function.


```r
print_hello()
```

```
## [1] "Hello"
```

## Arguments

Most of the functions we have used in these lessons have had at least one argument
inside of the parentheses. The `print_hello()` function did not have any arguments,
so we could run it without putting anything inside `()`. We could modify the
function to take an argument that pastes some text to the printed message.

Here we recreate the same function, but this time we add an argument `text` inside
of the parentheses. 


```r
print_hello <- function(text) {
  
  message <- paste("Hello", text)
  
  print(message)
  
}
```

Now there are two lines of code inside of the curly braces. The first line uses
the `paste()` function to concatenate two character values. The first value will
always be "Hello". The second value will be supplied by the user in the `text`
argument. 


```r
print_hello(text = "everybody!")
```

```
## [1] "Hello everybody!"
```

## Default Values

We can create a function with more than one argument, and set default values when
needed. Suppose we would like to make a function that checks if a measurement is
greater than a criteria pollutant standard. We could make a simple function that
takes two arguments: one for the measurement value, and one for the standard value.


```r
standard_violated <- function(measurement, standard) {
  
  measurement > standard
  
}
```

This function will simply return a `TRUE` or `FALSE` value, depending on whether
the measurement is greater than the standard or not.


```r
standard_violated(measurement = 84, standard = 70)
```

```
## [1] TRUE
```

We could write a more specific function for checking a value against the ozone
standard. For this function, we want to keep the `standard` parameter but make sure
the default is `70`. It may be that we typically want to use this function to 
check against the current 8-hour ozone standard in parts per billion, but have
the flexibility to use a different value. 

To set a default value, we use `= 70` when we create the function.


```r
standard_violated <- function(measurement, standard = 70) {
  
  measurement > standard
  
}
```

Now, when we use the function, it is not necessary to set the `standard` argument.


```r
standard_violated(measurement = 50)
```

```
## [1] FALSE
```

## Positional Arguments

One final note on functions in R. When a function is created, the order of the 
arguments are important. The user can supply values for the arguments in the order
they appeared in the parentheses of the `function( ){ }` call, without writing out
the argument names. 

For example, we can supply two numbers to the `standard_violated()` function that
we created above, without writing out the `measurement` and `standard` arguments.
When R executes the function, it will assign the numbers to the arguments
based on the position in the parentheses.

Here we show that using two numbers in a different order will return different
outputs.


```r
standard_violated(60, 70)
```

```
## [1] FALSE
```


```r
standard_violated(70, 60)
```

```
## [1] TRUE
```

# if Functions

Writing custom functions is a good way to standardize some R code that can be reused
on different data sets. It's also helpful to write code that will execute different
lines of code depending on different scenarios. The functions `if()` and `ifelse()`
allow you to control what code is executed based on a logical condition.

The `if()` function takes the logical condition in the parentheses. The code that
will run if the logical expression is `TRUE` is placed inside curly braces. Below
is the outline (not actual R code).


```r
if(<logical expression>) {
  
  <code that will run if the logical expression is TRUE>
  
} 
```

The key word `else` can also be used with another set of curly braces to hold
code that will only run if the logical expression returns `FALSE`


```r
if(<logical expression>) {
  
  <code that will run if the logical expression is true>
  
} else {
  
  <code that will run if the logical expression is false>
  
}
```

For example, if we wanted to print a message based on the value of ozone, we 
could use this construction:


```r
ozone <- 0.075

if(ozone > 0.065) {
  
  print("Potential Health Effects")
  
} else {
  
  print("All Good")
  
}
```

```
## [1] "Potential Health Effects"
```

Since the expression `ozone > 0.065` resolves to `TRUE`, the code in the first
set of curly braces is run. If we set the `ozone` variable to `0.06`, then the
logical expression will resolve to `FALSE` and the code in the second curly 
braces will run.


```r
ozone <- 0.06

if(ozone > 0.065) {
  
  print("Potential Health Effects")
  
} else {
  
  print("All Good")
  
}
```

```
## [1] "All Good"
```

The `ifelse()` function is another way to use a logical condition that determines
which output is returned. Here is the outline.


```r
ifelse(<test>, <yes>, <no>)
```

The `test` argument is the logical expression, `yes` is the value returned if
the expression resolves to `TRUE`, and `no` is the value returned if the expression
resolves to `FALSE`. 

Here we accomplish the same task as the previous example. This time we use the
`ifelse()` function to create a variable named `message`.


```r
ozone_value <- 0.06

message <- ifelse(ozone_value > 0.065, "Potential Health Effects", "All Good")

print(message)
```

```
## [1] "All Good"
```



# For loops

Like most programming languages, R has for and while loops. This tutorial will
cover just for loops and move on to `apply()` functions, which are more commonly 
used in R.

For loops are used to repeat an operation a set number of times. Here is the 
basic outline:


```r
for(i in sequence){
  
  <code that will run a set number of times>
  
}
```

The `sequence` parameter is typically a vector. The `i` parameter is a variable
that will take on the values in the `sequence` vector. For instance, if `sequence`
was the vector `c(1, 2, 3)` then the `i` variable will take on each of those values
in turn.

This example simply prints the values of the vector as the for loop progresses.


```r
for(i in c(1, 2, 3)) {
  
  print(i)
  
}
```

```
## [1] 1
## [1] 2
## [1] 3
```

Typically when we use loops, we want to perform the same operation on different
sets of data and save the results. To do this using the `for()` function in R,
we need to create an empty vector (or list or data frame) and save the results
during each iteration.

Here is an example data frame we will use. It represents a few values from three
monitors.


```r
monitors <- data.frame(monitor1 = c(50, 60, 58, 52),
                       monitor2 = c(55, 59, 65, 61),
                       monitor3 = c(70, 62, 68, 71))

monitors
```

```
##   monitor1 monitor2 monitor3
## 1       50       55       70
## 2       60       59       62
## 3       58       65       68
## 4       52       61       71
```

In the code below, we create an empty vector called `max_values`. As the `for()`
function loops through the vector `c(1, 2, 3)`, the data frame columns are accessed
using square brackets `[ , i]`. Each max value is saved to the `max_values` vector 
using square brackets `[i]`. 


```r
max_values <- c()

for(i in c(1, 2, 3)) {
  
  max_values[i] <- max(monitors[, i])
  
}

max_values
```

```
## [1] 60 65 71
```


# apply function

Although the for loop is common in programming languages, it is not the most 
efficient way to apply a function to different sets of data in R. The most efficient 
way to do loops in R is with the `apply()` family of functions, including `lapply()`, 
`tapply()`, and `mapply()`. This section will demonstrate how to use the `apply()`
function.

The `apply()` function takes a data frame (or matrix) as the first argument. The
second argument determines if each loop will apply to the rows (`1`) or columns 
(`2`). And the third argument is the function you want to apply to each row or column.
Additional arguments can be used to pass on to the function being applied to each
row or column.

The example below applies the `max()` function to the `monitors` data frame from
the previous section. 


```r
monitors_max <- apply(monitors, MARGIN = 2, FUN = max)

monitors_max
```

The `MARGIN` argument is set to `2` because we are applying
the `max()` function to the columns of the data frame. Also notice that we do
not need to create an initial empty vector, as we did with the `for()` function.
The returned value is a named vector that is as long as the number of columns
in the data frame.

We could also find the mean of each row in the `monitors` data frame. To do this,
we would set the `MARGIN` argument to `1`.


```r
apply(monitors, MARGIN = 1, FUN = mean)
```

```
## [1] 58.33333 60.33333 63.66667 61.33333
```

# Next Lesson

The next lesson in this series is on [Plotting](../5-Plotting/readme.md).

# Exercises

Try these exercises to test your comprehension of material in this lesson.

### Exercise 1

Write a function named `ppm_to_ppb` that converts a value from parts per million
to parts per billion.

<details><summary>Click for Solution</summary>


#### Solution


```r
ppm_to_ppb <- function(value) {
  
  value * 1000
  
}
```

</details>

---

### Exercise 2

Write a function named `check_value` that prints "warning" if a value is above a 
threshold, and "OK" if it's below. Make the threshold an argument in the function.

<details><summary>Click for Solution</summary>


#### Solution


```r
check_value <- function(value, threshold) {
  
  if(value > threshold) {
    
    print("warning")
    
  } else {
    
    print("OK")
    
  }
  
}
```

</details>

---

### Exercise 3

Use the `for()` function to loop through the `temp` column of the `chicago_air`
data frame and print any value that is above 90 degrees.

<details><summary>Click for Solution</summary>



#### Solution


```r
for (i in chicago_air$temp) {
  
  if(i > 90) {
    
    print(i)
    
  }
  
}
```

```
## [1] 91
## [1] 93
## [1] 91
```

</details>

---

### Exercise 4

Use the `apply()` function to create a vector of the mean values from the numeric
columns in the `chicago_air` data frame.

<details><summary>Click for Solution</summary>


#### Solution

> Subset the `chicago_air` data frame to a new data frame with just the numeric
columns: `ozone`, `temp`, and `pressure`. Pass the subset data frame, and the 
`mean` function, to the `apply()` function. Use `MARGIN = 2` and `na.rm = TRUE`
to make sure all `NA` values are removed.



```r
chicago_numeric <- chicago_air[, c("ozone", "temp", "pressure")]

mean_values <- apply(chicago_numeric, MARGIN = 2, FUN = mean, na.rm = TRUE)

mean_values
```

```
##        ozone         temp     pressure 
## 3.665014e-02 6.352603e+01 1.004354e+03
```

</details>
