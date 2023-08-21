# Lesson 5: Plotting with ggplot2

In this lesson, we will learn how to create publication-quality graphics in R using the `ggplot2` package. `ggplot2` is a powerful visualization library that allows us to create a wide range of plots, such as scatter plots, line charts, bar charts, and histograms. We will also explore how to customize the appearance of plots and generate multiple conditional plots using facets.

At the end of this lesson, you will be able to:

- Make basic plots like scatter plots, line charts, bar charts, and histograms using `ggplot2`.
- Customize the appearance of plots by modifying colors, labels, titles, legends, and other visual elements.
- Use facets to generate multiple plots conditioned on variables.

## Introduction to ggplot2

`ggplot2` is a popular data visualization package in R created by Hadley Wickham. It follows a layered approach to creating plots, allowing you to build and modify plots incrementally. 

The basic syntax of a `ggplot2` plot consists of three main components:

- Data: The dataset that contains the variables you want to plot.
- Aesthetics (aes): The mapping between variables in the dataset and visual properties of the plot, such as position, color, and size.
- Geometries (geoms): The type of plot you want to create, such as points, lines, bars, or areas.

Let's start by creating a simple scatter plot using the `ggplot2` syntax:

```R
library(ggplot2)

# Load the dataset
data <- read.csv("data/chicago_air.csv")

# Create a scatter plot
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point()
```

In this example, we use the `ggplot()` function to specify the dataset `data` and the `aes()` function to map the variables `temp` and `ozone` to the x and y axes, respectively. The `geom_point()` function is used to add the points to the plot.

## Basic Visualization Types

`ggplot2` provides a wide range of geoms to create different types of plots. Let's explore a few examples:

### Scatter Plot

To create a scatter plot, use the `geom_point()` function:

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point()
```

![scatter_plot](images/scatter_plot.png)

### Line Chart

To create a line chart, use the `geom_line()` function:

```R
ggplot(data, aes(x = date, y = ozone)) +
  geom_line()
```

![line_chart](images/line_chart.png)

### Bar Chart

To create a bar chart, use the `geom_bar()` function:

```R
ggplot(data, aes(x = month, fill = factor(month))) +
  geom_bar()
```

![bar_chart](images/bar_chart.png)

### Histogram

To create a histogram, use the `geom_histogram()` function:

```R
ggplot(data, aes(x = ozone)) +
  geom_histogram()
```

![histogram](images/histogram.png)

## Customizing Plots

`ggplot2` provides a wide range of options to customize the appearance of your plots. You can modify colors, labels, titles, legends, and other visual elements to make your plots more informative and visually appealing.

### Themes

You can apply different themes to your plots to change the overall appearance. `ggplot2` provides several built-in themes, such as `theme_bw()`, `theme_classic()`, and `theme_minimal()`. You can apply a theme by adding it to your plot using the `+` operator.

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point() +
  theme_bw()
```

### Axis Labels

You can add labels to the x and y axes using the `xlab()` and `ylab()` functions.

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point() +
  xlab("Temperature") +
  ylab("Ozone")
```

### Legends

To add a legend to your plot, use the `labs()` function and specify the `fill` or `color` argument with the desired label.

```R
ggplot(data, aes(x = month, fill = factor(month))) +
  geom_bar() +
  labs(fill = "Month")
```

You can also modify the position, title, and appearance of the legend using the `theme()` function.

### Titles

To add a title to your plot, use the `ggtitle()` function.

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point() +
  ggtitle("Temperature vs. Ozone")
```

## Conditional Plots with Facets

Facets allow you to generate multiple plots conditioned on variables in your dataset. This is useful when you want to compare subsets of your data or visualize relationships across different groups.

To use facets, you can add the `facet_wrap()` or `facet_grid()` function to your plot.

### `facet_wrap()`

The `facet_wrap()` function creates multiple plots arranged in a "wrap" layout. It takes in a formula specifying the variables to be used for conditioning.

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point() +
  facet_wrap(~ month)
```

This will create a separate plot for each month of the year.

### `facet_grid()`

The `facet_grid()` function creates multiple plots arranged in a grid layout. It takes in two formulas specifying the variables to be used for conditioning on the rows and columns, respectively.

```R
ggplot(data, aes(x = temp, y = ozone)) +
  geom_point() +
  facet_grid(month ~ weekday)
```

This will create a grid of plots, with each row representing a month and each column representing a weekday.

## Summary

In this lesson, we learned how to create plots using the `ggplot2` package in R. We explored different types of plots such as scatter plots, line charts, bar charts, and histograms. We also learned how to customize the appearance of plots by modifying various visual elements. Finally, we learned how to use facets to generate multiple plots conditioned on variables. With these capabilities, we can create professional-quality graphics to visualize and communicate our data effectively.

## Up Next

In the next lesson, we will learn how to calculate common descriptive and inference statistics in R using base R functions. We will explore how to calculate summary statistics, generate confidence intervals, and perform statistical tests such as t-tests and ANOVA analysis. Get ready to dive into the world of statistics in R!

