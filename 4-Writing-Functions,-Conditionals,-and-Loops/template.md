# Lesson 4: Writing Functions, Conditionals, and Loops

In this lesson, we will learn how to write custom functions in R, use if/else statements to control program flow, and
utilize loops to iterate over data or code segments.

## Writing Functions in R

Functions are blocks of reusable code that can take input values, perform specific tasks, and return output values. Writing
functions can help to modularize your code and improve its readability and maintainability.

To define a function in R, you use the `function` keyword followed by the function name and parentheses. Inside the
curly braces `{}`, you define the code that the function will execute. You can also specify input arguments for the
function within the parentheses.

Here's an example of a function that calculates the average of two numbers:

```R
average <- function(x, y) {
  result <- (x + y) / 2
  return(result)
}
```

In this example, the function `average` takes two input arguments: `x` and `y`. It calculates their average and assigns the
result to the variable `result`. Finally, it returns the value of `result` using the `return` keyword.

You can call the `average` function by passing in two numbers, like this:

```R
result <- average(10, 20)
```

The function will return the average of 10 and 20, which will be assigned to the variable `result`.

### Key Points

- Functions in R are defined using the `function` keyword followed by the function name and parentheses.
- You can specify input arguments for the function within the parentheses.
- Inside the function, code is written within curly braces `{}`.
- Use the `return` keyword to specify the value that the function should return.

## Using if/else Statements

In R, you can use if/else statements to control the flow of your program based on certain conditions. These conditional
statements allow you to execute different blocks of code depending on whether a condition is true or false.

The general syntax of an if/else statement is as follows:

```R
if (condition) {
  # code to execute if the condition is true
} else {
  # code to execute if the condition is false
}
```

The `condition` is an expression that evaluates to either `TRUE` or `FALSE`. If the condition is `TRUE`, the code block
inside the first set of curly braces `{}` will be executed. If the condition is `FALSE`, the code block inside the second
set of curly braces `{}` will be executed.

Here's an example that illustrates the use of if/else statements:

```R
x <- 10

if (x > 5) {
  print("x is greater than 5")
} else {
  print("x is less than or equal to 5")
}
```

In this example, the condition `x > 5` is evaluated. Since the value of `x` is 10, which is greater than 5, the code block
inside the first set of curly braces `{}` will be executed. As a result, the message "x is greater than 5" will be printed to
the console.

You can also use multiple if/else statements to handle more complex conditions:

```R
x <- 10

if (x > 10) {
  print("x is greater than 10")
} else if (x == 10) {
  print("x is equal to 10")
} else {
  print("x is less than 10")
}
```

In this example, the condition `x > 10` evaluates to `FALSE`, so the first code block is not executed. The condition
`x == 10` evaluates to `TRUE`, so the code block inside the second set of curly braces `{}` is executed, resulting in the
message "x is equal to 10" being printed to the console.

### Key Points

- If/else statements allow you to control program flow based on conditions.
- Conditions are expressions that evaluate to either `TRUE` or `FALSE`.
- You can have multiple if/else statements to handle different conditions.

## Iterating with Loops

Loops are used in programming to repeat a specific block of code multiple times. In R, there are two types of loops:
*for* loops and *while* loops.

### For Loops

A *for* loop allows you to iterate over a sequence of values. The basic syntax of a *for* loop is as follows:

```R
for (variable in sequence) {
  # code to execute
}
```

The `variable` represents the loop variable, and `sequence` defines the range of values the loop variable will take.
Within the loop, you can perform operations on the loop variable.

Here's an example that demonstrates the use of a *for* loop:

```R
for (i in 1:5) {
  print(i)
}
```

In this example, the loop variable `i` takes on the values 1, 2, 3, 4, and 5. The loop iterates 5 times, and during each
iteration, the value of `i` is printed to the console.

### While Loops

A *while* loop allows you to repeat a block of code as long as a certain condition is true. The basic syntax of a
*while* loop is as follows:

```R
while (condition) {
  # code to execute
}
```

The `condition` is an expression that is evaluated before each iteration of the loop. If the condition is `TRUE`, the code
block inside the loop will be executed. The loop will continue to iterate until the condition becomes `FALSE`.

Here's an example that demonstrates the use of a *while* loop:

```R
i <- 1

while (i <= 5) {
  print(i)
  i <- i + 1
}
```

In this example, the loop starts with `i` equal to 1. The condition `i <= 5` is true, so the code block within the loop is
executed. The value of `i` is printed to the console, and `i` is incremented by 1. This process repeats until `i` becomes
greater than 5, at which point the condition becomes false and the loop terminates.

### Key Points

- Loops allow you to repeat a specific block of code multiple times.
- *For* loops iterate over a sequence of values.
- *While* loops repeat as long as a certain condition is true.

## Applying Functions, Conditionals, and Loops

Now that we have learned about writing functions, using if/else statements, and employing loops, let's see how we can
apply these concepts to automate data processing tasks.

Here's an example that demonstrates the use of a function, if/else statement, and loop to process a dataset:

```R
# Function to calculate the mean of a vector
calculate_mean <- function(data) {
  sum <- 0
  count <- 0
  
  for (value in data) {
    sum <- sum + value
    count <- count + 1
  }
  
  if (count > 0) {
    mean <- sum / count
    return(mean)
  } else {
    return(NULL)
  }
}

# Dataset
values <- c(3, 5, 8, 2, 9, 10)
mean_value <- calculate_mean(values)

if (!is.null(mean_value)) {
  print(paste("Mean: ", mean_value))
} else {
  print("Unable to calculate mean.")
}
```

In this example, we have defined a function `calculate_mean` that takes in a vector of values and calculates their mean.
We use a *for* loop to iterate over the vector, summing up the values and counting the number of values. We then use
an *if/else* statement to check if any values were counted. If there were values, we calculate and return the mean. If no
values were counted, we return `NULL`.

The dataset `values` contains a set of numbers, and we calculate the mean using the `calculate_mean` function. If the mean
value is not `NULL`, we print the mean value. Otherwise, we print a message indicating that the mean could not be
calculated.

### Key Points

- Functions, conditionals, and loops can be combined to automate data processing tasks.
- Functions can encapsulate repetitive tasks.
- Use conditionals to perform different actions based on specific conditions.
- Loops can iterate over data or code segments to repeat operations.

## Summary

In this lesson, we learned how to write custom functions in R, use if/else statements to control program flow, and employ
loops to repeat code segments. We saw how these concepts can be applied to automate data processing tasks, resulting in more
efficient and reusable code.

Now that we have a solid understanding of writing functions, conditionals, and loops, we can move on to the next lesson
where we will explore the topic of Plotting with ggplot2.

Up Next: [Lesson 5: Plotting with ggplot2](./5-Plotting-with-ggplot2/readme.md)