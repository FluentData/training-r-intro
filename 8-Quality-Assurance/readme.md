# Quality Assurance

Before we perform any kind of analysis, it is important to understand the distributions of our data. **summary()** function is a quick way to get basic stats about your data like minimum, maximum, median, mean, 1st quartile and 3rd quartile.

```r
summary(chicago_air$pollution)
```

We can also visualize the distribution with histograms.

```r
hist(chicago_air$pollution)
```

> _**Info:** Histograms divide the data into bins and represent data distribution by plotting the frequency of the bins. They provide a visual representation of data distribution._

## Table of Contents

1. [Checking Distributions](#checking-distributions)
1. [Visual Data Inspection](#visual-data-inspection)
1. [Checking Data Properties: Outliers and Ranges](#checking-data-properties-outliers-and-ranges)
1. [Automating Quality Assurance](#automating-quality-assurance)

## Visual Data Inspection

Scatter plots and density plots are other tools that can help us understand our data better.

Scatter plots can give us some intuition into the relationship between two variables.

```r
plot(chicago_air$pollution, chicago_air$temp)
```

Then we can use density plots to visualize the distribution of a single variable. The y-axis is the density which depends on the count and becomes a probability when integrated over the range of x values.

```r
plot(density(chicago_air$pollution))
```

#### Exercise

Make a scatter plot between 'ozone' and 'temp' variables for the 'quality_air' dataset. Then plot the density plot for 'ozone'.

<details><summary>Click for Hint</summary>

Use the plot() function for creating scatter and density plots.

</details>
<details><summary>Click for Solution</summary>

plot(quality_air$ozone, quality_air$temp)
plot(density(quality_air$ozone))
      
> Visual Inspection helps to understand data and its relationships better. Scatter plots show relationship between two variables. Density plots provide a visual representation of data distribution.
</details>

---

## Checking Data Properties: Outliers and Ranges

Checking if the values are within the expected range can help identify entry errors or other problems.

```r
any(chicago_air$pollution < 0)
```

Identifying outliers with boxplots:

```r
boxplot(chicago_air$pollution, main = "Boxplot of Air Pollution", ylab="Pollution")
```

> _**Info:** Boxplots provide a summary of the minimum, first quartile, median, third quartile, and maximum in a visual way. We can also identify outliers (if present) using whisker of the boxplot._

#### Exercise

Check if any of the 'ozone' values in the 'quality_air' dataset is less than 0. Then create a boxplot for the same variable.

<details><summary>Click for Hint</summary>

Use the any() function to check for negative values.

</details>
<details><summary>Click for Hint</summary>

To plot a boxplot, use the boxplot() function.

</details>
<details><summary>Click for Solution</summary>

any(quality_air$ozone < 0)
boxplot(quality_air$ozone, main = 'Boxplot of Ozone', ylab='Ozone')
      
> It's important to check if the data values are within expected ranges and identify outliers. The any() function can check for specific conditions. Boxplots visually summarize data and can help identify outliers.
</details>

---

## Exercises

#### Exercise 1

Write a function named 'var_distribution' that takes a dataset and a variable then does the following: Prints the summary, draws histogram, creates scatter plot with temperature, and draws a density plot.

<details><summary>Click for Hint</summary>

Create a function 'var_distribution' and input a data frame and a variable.

</details>
<details><summary>Click for Hint</summary>

The function should print the summary, draw histogram, create scatter plot with temperature and draw density plot.

</details>
<details><summary>Click for Solution</summary>

var_distribution <- function(df, var){
   print(summary(df[,var]))
   hist(df[,var])
   plot(df[,var], df$temp)
   plot(density(df[,var]))
}
var_distribution(quality_air, 'ozone')
      
> This exercise requires students to apply the concepts learned in multiple sections of the lesson, reinforcing their understanding of how to analyse data distributions and visualize them.
</details>

---

#### Exercise 2

Write a function named 'qa_fullcheck' that takes a dataset and a variable then does the following: Prints the summary, draws histogram, checks if any value is less than zero, draws boxplot, and creates scatter plot with temperature.

<details><summary>Click for Hint</summary>

Create a function 'qa_fullcheck' and input a data frame and a variable.

</details>
<details><summary>Click for Hint</summary>

The function should print the summary, draw histogram, print any negative values, create boxplot and a scatter plot with temperature.

</details>
<details><summary>Click for Solution</summary>

qa_fullcheck <- function(df, var){
   print(summary(df[,var]))
   hist(df[,var])
   print(any(df[,var] < 0))
   boxplot(df[,var], main = paste('Boxplot of', var), ylab=var)
   plot(df[,var], df$temp)
}
qa_fullcheck(quality_air, 'ozone')
      
> This exercise combines all the concepts taught in the lesson. Students are asked to perform data check, histrogram, checking any negative values, boxplot and scatter plot on a dataset in R.
</details>

---

#### Exercise 3

Imagine we have a list of variables of interest from the 'quality_air' dataset ['ozone', 'so2', 'pm25']. Write a loop to perform automated quality assurance for each of these variables using your qa_check function.

<details><summary>Click for Hint</summary>

Create a vector of variables of interest.

</details>
<details><summary>Click for Hint</summary>

Write a for loop to apply the 'qa_check' function on each variable.

</details>
<details><summary>Click for Solution</summary>

vars <- c('ozone', 'so2', 'pm25')
for (var in vars){
   qa_check(quality_air, var)
}
      
> Iteration (like for-loop) is a powerful tool in programming, it enables us to perform a task multiple times, which is useful in cases like this: applying a checking function to multiple variables in a dataset.
</details>

---

## Automating Quality Assurance

Instead of manually checking every dataset, we can write functions to automate this.

```r
qa_check <- function(df, var){
  print(summary(df[,var]))
  plot(density(df[,var]))
  print(any(df[,var] < 0))
  boxplot(df[,var])
}

# Call the function on pollution data
qa_check(chicago_air, "pollution")
```

By making a report that compiles all these checks for all variables, we can quickly identify any potential data issues.

---

Congratulations, you made it to the end of the Introduction to R for Air Quality Data Science course! In today's lesson, we've learned how to perform some basic quality assurance checks on our data to ensure that it's clean and ready to use. We've looked into histograms, density plots, scatter plots, and box plots. We also automated our QA tasks with functions. Your newfound knowledge on cleaning and preparing data will prove incredibly useful in your day-to-day data science tasks!

Happy Coding!

_Up next, check out more advanced topics in R and environmental science with **[R for Environmental Data Analysis](../r-for-environmental-data-analysis/readme.md)**._

#### Exercise

Write an automated quality assurance function for the 'ozone' variable from the 'quality_air' dataset.

<details><summary>Click for Hint</summary>

Create a function that takes a data frame and a variable as input.

</details>
<details><summary>Click for Hint</summary>

The function should perform these operations: Print summary, plot density, check for negative values and create a boxplot.

</details>
<details><summary>Click for Solution</summary>

qa_check <- function(df, var){
    print(summary(df[,var]))
    plot(density(df[,var]))
    print(any(df[,var] < 0))
    boxplot(df[,var])
 }
qa_check(quality_air, 'ozone')
      
> Automating this process allows you to perform quality assurance more efficiently, which is particularly useful when dealing with multiple datasets or variables.
</details>

---

