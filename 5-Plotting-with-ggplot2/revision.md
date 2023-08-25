# Plotting in R: Built-in and ggplot2

## Introduction

In the previous lessons, we learned about working with data in R including how to load, manipulate, and inspect datasets. Now, we are going to learn about a crucial part of data analysis: visualization. We'll start by introducing some of the most common plotting functions built into R like `plot()`, `hist()`, and `boxplot()`. We'll then dig deeper into `ggplot2`, a powerful and flexible data visualization package in R that uses a layered approach to plot building. By the end of this lesson, you'll understand why `ggplot2` is often the go-to package for creating statistical graphics in R. 

## Built-in Plot Functions

We'll start with the built-in functions R provides for creating simple plots. These include:

- **plot()**: Line and scatter plots
- **hist()**: Histograms
- **boxplot()**: Box plots

All these functions work with a wide array of data types including vectors and data frames. Let's dive right into it and create some plots. For this, we will use the `mtcars` dataset.

### Line and Scatter Plots with plot()

The most basic plotting function in R is `plot()`. It creates a scatter plot by default, but can also be used to create line plots by passing an extra argument.

``` r
# Load the dataset
data(mtcars)

# Create a scatter plot of MPG against horsepower
plot(mtcars$hp, mtcars$mpg,
     xlab = "Horsepower",
     ylab = "Miles per Gallon",
     main = "MPG vs Horsepower")
```

### Histogram with hist()

Next, let's use the `hist()` function to create a histogram of `mpg` (miles per gallon).

``` r
# Create a histogram of 'mpg'
hist(mtcars$mpg,
    xlab = "Miles per Gallon",
    main = "Histogram of MPG")
```

### Boxplot with boxplot()

Let's create a boxplot to visualize the distribution and describe location, dispersion and skewness of `mpg` data, a key graphical tool of exploratory data analysis (EDA).

```r
boxplot(mtcars$mpg,
  main = "Box Plot of MPG",
  ylab = "Miles Per Gallon"
)
```

## Introduction to ggplot2

`ggplot2` is a powerful and flexible data visualization package in R. It uses a layered approach to plot building, which allows you to add, remove or change components in a straightforward, transparent manner.
Let's begin by installing and loading the `ggplot2` package.

``` r
# install.packages('ggplot2')
library(ggplot2)
```

Now we are ready to use `ggplot2` to make some plots! A `ggplot2` graphic is built up by adding different components, or "layers", to the plot, each of which contributes some part of the final image. The process is generally as follows:

1.Start with the `ggplot()` function where we specify the dataset and map variables to aesthetics.
2.Add `geoms` – geometric objects like points (`geom_point`) for scatter plots, bars (`geom_bar`) for bar plots, or lines (`geom_line`) for line plots.
3.Customize and refine the plot with additional layers like labels, themes, facets etc.

Let’s see how each of these steps works.

### Scatter Plot

For our first plot, let’s recreate the scatter plot of MPG against horsepower using the `mtcars` dataset.

``` r
# Create a scatter plot
ggplot(mtcars, aes(x=hp, y=mpg)) +
  geom_point()+
  labs(title = "Scatter plot of MPG against Horsepower")
```

### Histogram

Once again, let's create a histogram of `mpg` (miles per gallon).

``` r
# Histogram
ggplot(mtcars, aes(x=mpg)) +
  geom_histogram(binwidth=2, fill="blue", color='black') +
  labs(title = "Histogram of MPG")
```

### Customizing the Scatter Plot

The plot above is pretty basic. Let’s customize it by adding color, title and labels.

``` r
# Customized scatter plot
ggplot(mtcars, aes(x=hp, y=mpg)) +
  geom_point(color="blue") +
  xlab("Horsepower") +
  ylab("Miles per Gallon")
```

Reviewing these steps again:

- We provide our data to the ggplot function
- Set up a coordinate system with x and y mapping
- Use a point geometry (`geom_point`) to represent our data
- Finally, we customized the plot by changing the color of the points and the labels of the x and y axes

## Exercises

To get the most from this lesson, it's crucial to put these principles into practice. Here are few exercises you should try out.

1.Using the `mtcars` dataset, create a scatter plot of `mpg` (y) against `disp` (times disp).
2.Create a histogram for the `airquality` dataset in R, plotting the distribution of `Ozone` (Ozone (ppb)).
3.Combine what you've learned to create a scatter plot of `mpg` (miles/gallon) against `wt` (weight), facets the plot by `cyl` (number of cylinders), and customize it with a title and x and y axis labels.

## Up Next

In this lesson, we introduced plotting in R. We covered the basic structure and use of the `ggplot()` function and several geoms, and we practiced creating and customizing different types of plots.
In the [next lesson](../6-Basic-Statistics-in-R), we will learn about basic statistics in R. Statistical analysis is a key component of data analysis, and understanding basic statistics is essential for every data analyst. See you there!