# Writing Functions, Conditionals, and Loops

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

## Table of Contents

1. [Functions in R](#functions-in-r)
1. [If/Else Statements](#if-else-statements)
1. [Iteration with For and While Loops](#iteration-with-for-and-while-loops)
1. [Putting It All Together](#putting-it-all-together)
1. [Up Next](#up-next)

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

#### Exercise

Write an If/Else statement that prints whether a given number is even or odd.

<details><summary>Click for Hint</summary>

Use `%%` operator to get the remainder of a division.

</details>
<details><summary>Click for Hint</summary>

An even number gives a remainder of 0 when divided by 2.

</details>
<details><summary>Click for Solution</summary>

num <- 4
if(num %% 2 == 0) {print("Number is even")} else {print("Number is odd")}
      
> This statement checks if a number is divisible by 2 (which means it's even). If yes, it prints 'Number is even', otherwise it prints 'Number is odd'.
</details>

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

## Exercises

#### Exercise 1

Write a function in R that accepts an array as input and returns its mean value.

<details><summary>Click for Hint</summary>

Use the `function` keyword to define the function.

</details>
<details><summary>Click for Hint</summary>

Inside the function, use `sum()` to calculate the total sum of the array, and `length()` to get the number of elements.

</details>
<details><summary>Click for Hint</summary>

Divide the total sum by the number of elements to get the mean.

</details>
<details><summary>Click for Solution</summary>

mean_value <- function(arr) {return(sum(arr) / length(arr))}
      
> This function calculates the mean of an array. It uses the sum function to calculate the sum of the elements, and the length function to calculate the number of elements. Then it divides the sum by the number of elements to get the mean.
</details>

---

#### Exercise 2

Write an R function that accepts an integer as input and uses a `while` loop to calculate the factorial of the input number.

<details><summary>Click for Hint</summary>

The factorial of a number is the product of all positive integers less than or equal to that number.

</details>
<details><summary>Click for Hint</summary>

Use a `while` loop to multiply all positive integers less than or equal to the input number.

</details>
<details><summary>Click for Solution</summary>

factorial_num <- function(num) {
 factorial = 1
 while(num > 1) {
  factorial = factorial * num 
  num = num - 1
 } 
 return(factorial)
}
      
> This function calculates the factorial of a number. It initializes `factorial` to 1. Then it enters a `while` loop, which continues as long as `num` is greater than 1. In each iteration, it multiplies `factorial` by `num` and then decreases `num` by 1. Finally, it returns the value of `factorial`.
</details>

---

#### Exercise 3

Write a function in R that accepts an array and a number as input, and returns the number of elements in the array that are greater than the input number.

<details><summary>Click for Hint</summary>

Use a `for` loop to iterate over each element of the array.

</details>
<details><summary>Click for Hint</summary>

Inside the loop, use an `if` statement to check if the current element is greater than the input number.

</details>
<details><summary>Click for Hint</summary>

If it is, increment a counter.

</details>
<details><summary>Click for Solution</summary>

count_greater <- function(nums, num) { 
 count = 0 
 for(i in nums) { 
 if(i > num) { 
 count = count + 1 
 } 
 } 
 return(count) 
}
      
> This function counts the number of elements in an array that are greater than a given number. It accomplishes this by looping over each element in the array. For each element, it checks if it is greater than the input number. If it is, it increments a counter. The final count is returned.
</details>

---

## Up Next

In this lesson, we covered some of the fundamental concepts of R programming including how to define our own functions, use control logic with `if/else` statements and automating tasks with `for` and `while` loops. In essence, these concepts should provide the foundation for automating your data processing tasks on air quality datasets.

Taking it a step further, in the [next lesson](../5-Plotting-with-ggplot2/readme.md), we'll delve into creating publication-quality graphics using `ggplot2`!

