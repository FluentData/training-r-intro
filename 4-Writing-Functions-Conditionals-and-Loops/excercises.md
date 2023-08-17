## Exercises


### Exercise 1

Exercise 1: Write a function `myMax()` in R, which calculates the maximum value of a numeric vector. Check your function by comparing its output with the built-in `max()` function of R for a numeric vector.

<details><summary>Click for Hint</summary>

First, create the `myMax` function. This function should take an array of numbers as an argument and return the maximum value from that array. Make sure to use the `max()` function inside your `myMax` function.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# The myMax function
myMax <- function(x) {
  max_value <- max(x)
  return(max_value)
}

# Creating a numeric vector
my_vector <- c(1, 23, 5, 77, 0, 12)

# Using myMax on my_vector
print(myMax(my_vector))

# Using max on my_vector
print(max(my_vector))
```
```

#### Output

```r
```r
# Both outputs should be the same
[1] 77
[1] 77
```
```



</details>

---


### Exercise 2

Exercise 2: Write a conditional if-else statement in R to check if a number is greater than 0. If the number is positive print 'Positive', else print 'Negative or Zero'.

<details><summary>Click for Hint</summary>

You will use `if` and `else` to implement this check. The `if` part will check if the number is more than 0 and print 'Positive'. The `else` part will be executed if the `if` condition is not satisfied and will print 'Negative or Zero'.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# Number to check
check_number <- -1

# If-else statement
test_number <- function(x) {
if (x > 0) {
print('Positive')
} else {
print('Negative or Zero')
}
}

test_number(check_number)

# Changing number to check
check_number <- 5

test_number(check_number)
```
```

#### Output

```r
```r
# Output
test_number(-1)
"Negative or Zero"
test_number(5)
"Positive"
```
```



</details>

---


### Exercise 3

Exercise 3: Write a for loop in R that prints the cube of numbers from 1 to 5.

<details><summary>Click for Hint</summary>

You can use `for(i in 1:5)` to create a loop that will iterate from 1 to 5. In each iteration, print the cube of `i` using the `print` function and the cube operator `^3`.
</details>
<details><summary>Click for Solution</summary>

#### Solution

```r
```r
# For loop to print the cube of numbers from 1 to 5
for(i in 1:5) {
    print(i^3)
}
```
```

#### Output

```r
```r
# Output
[1] 1
[1] 8
[1] 27
[1] 64
[1] 125
```
```



</details>

---

