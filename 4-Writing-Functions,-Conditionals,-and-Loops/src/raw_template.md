# Writing Functions, Conditionals, and Loops

In our [previous lesson](../3-Subsetting-Sorting-and-Combining-Data/readme.md), we learned about subsetting, sorting and combining datasets in R. We used elementary methods to make this happen. However, to improve the efficiency of our tasks in the long run, we need to leverage the automation power of R by writing reusable functions and implementing control flow using `if/else` statements and loops. In this lesson, we're going to dive into how to implement these methods in R.

---

## Functions in R

When performing a unique task repeatedly, creating a custom function can save us time by improving efficiency and readability. Functions are the basic building blocks of R programming, and they in-turn help in building more complex pieces of code. Let's start learning about how to write our own functions!

### Defining a Custom Function

In R, a set of code can be encapsulated into a function using the `function()` keyword, where each function is a named sequence of statements.

```r
my_function <- function() {
    # Code here
}

# Call the function
my_function()
```

### Function Arguments

A function, with no arguments, as in the above example, is not very useful. We can add parameters to a function by specifying them in the brackets of the `function()` call.

```r
# A function to calculate the square of a number
square_num <- function(num) {
    return(num * num)
}

# Call the function
square_num(4) # returns 16
```

In this function, `num` is an argument to the function and it's passed as a number to the function call.

---

## If/Else Statements

If/Else statements are used to execute a certain piece of code only when some conditions are met. This can come in handy when we want to control the code flow based on conditional logic.

```r
# If statement
num <- 10
if (num > 5) {
   print("Number is greater than 5")
}

# If/Else statement
if (num > 15) {
   print("Number is greater than 15")
} else {
   print("Number is not greater than 15")
}
```

---

## Iteration with For and While Loops

Loops are powerful programming constructs which allow you to repeat a piece of code a certain number of times. We'll cover two types of loops - `for` and `while`.

### For Loops

A `for` loop is used for iterating over a sequence, usually a vector or a list, or until a certain condition is met.

```r
# For loop
for (i in 1:5) {
   print(i)
}
```

In the above code, the loop will run 5 times printing values from 1 to 5.

### While Loops

A `while` loop executes repeatedly until a certain condition is met.

```r
# While loop
num <- 0
while (num < 5) {
    print(num)
    num <- num + 1
}
```

The loop will run until `num` is smaller than 5.

---

## Putting It All Together

Once you have understanding about functions, conditionals and loops, you can begin to apply these concepts to automate data processing tasks. For instance, we could write a function that calculates mean of air quality parameters using `for` loop and `if/else` statements, making repetitive tasks much easier.

```r
# Placeholder for code block using chicago_aqs.csv
```

---

## Up Next

In this lesson, we covered some of the fundamental concepts of R programming including how to define our own functions, use control logic with `if/else` statements and automating tasks with `for` and `while` loops. In essence, these concepts should provide the foundation for automating your data processing tasks on air quality datasets.

Taking it a step further, in the [next lesson](../5-Plotting-with-ggplot2/readme.md), we'll delve into creating publication-quality graphics using `ggplot2`!