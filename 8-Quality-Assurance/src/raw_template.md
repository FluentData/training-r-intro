# Quality Assurance

As we have discussed before, the real-world data is often messy and requires a lot of cleaning. In this lesson, we will focus on some important aspects of quality assurance in data science like checking for outliers and uncommon values. We'll also learn how we can improve the quality of our data and automate these quality assurance tasks.

_After completing this lesson, you will be able to:_

- Check for outliers and common data issues
- Use visual tools to perform quality assurance
- Write functions to automate these QA checks

## Checking Distributions

Before we perform any kind of analysis, it is important to understand the distributions of our data. **summary()** function is a quick way to get basic stats about your data like minimum, maximum, median, mean, 1st quartile and 3rd quartile.

```r
summary(chicago_air$pollution)
```

We can also visualize the distribution with histograms.

```r
hist(chicago_air$pollution)
```

> _**Info:** Histograms divide the data into bins and represent data distribution by plotting the frequency of the bins. They provide a visual representation of data distribution._

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