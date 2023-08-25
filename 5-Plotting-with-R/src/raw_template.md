# Plotting with R

In our previous lesson, we learned how to automate repetitive tasks and control the flow of our programs by writing custom [functions, conditionals, and loops](./4-Writing-Functions-Conditionals-and-Loops/readme.md). Today, we are going to shift our focus to creating visualizations using R's plotting capabilities.

Creating meaningful and informative visualizations is a vital part of data analysis. A good graph can tell a story, giving insight into patterns and trends in data that are not immediately obvious from looking at raw numbers. R provides a variety of functions for creating plots, both in the base R package and in popular plotting packages like ggplot2. 

## Objectives

By the end of this lesson, you will be able to:
- Create basic plots like scatter plots, line plots, box plots, and histograms
- Customize the appearance of plots
- Generate multiple condition-specific plots using facets

## Base R Plots 

We start by creating simple plots using built-in R functions. Base R provides several functions for creating plots.

### Scatter Plots with plot()

Let's start by creating a scatter plot. We will use the `airquality` dataset that comes built-in with R. This dataset contains information about the air quality measurements recorded in New York.

```R
data(airquality)
head(airquality)

plot(airquality$Temp, airquality$Ozone, 
     main = "Temperature vs Ozone Levels", 
     xlab = "Temperature (in Fahrenheit)", 
     ylab = "Ozone (in ppb)")
```

Here, `plot()` is a versatile function that creates a scatter plot by default. The first two arguments are the x and y-variables. The `main` argument adds a title to the plot, and `xlab` and `ylab` label the x and y-axes respectively.

### Histograms with hist()

Histograms are great for visualizing the distribution of a single numerical variable. Here we use `hist()` to create a histogram of wind speeds from the `chicago_wind.csv` data.

```R
# import data
chicago_wind <- read.csv("data/chicago_wind.csv")

# create histogram
hist(chicago_wind$wind_speed, 
     main = "Histogram of Wind Speeds", 
     xlab = "Wind Speed (in mph)", 
     ylab = "Frequency", 
     col = "lightblue")
```

The `col` argument is used to fill the bars with a light blue color.

### Boxplots with boxplot()

Boxplots provide a graphical representation of the five-number summary of a dataset. Let's create a boxplot for the ozone levels in our airquality dataset. 

```R
# create boxplot
boxplot(airquality$Ozone, 
        main = "Boxplot of Ozone Levels", 
        xlab = "Ozone Levels", 
        ylab = "Frequency", 
        col = "lightgreen")
```

## Introduction to ggplot2

While base R provides many functions for creating plots, the `ggplot2` package, which is part of the `tidyverse` suite of packages, provides a more powerful and flexible system for creating plots.

To use ggplot2, you first need to install it with `install.packages("ggplot2")` and load it with `library(ggplot2)`.

### Scatter Plots with ggplot2

Here's how you can recreate the scatter plot we previously made with `plot()` using `ggplot()` instead:

```R
# load ggplot2
library(ggplot2)

# scatter plot with ggplot2
ggplot(airquality, aes(x = Temp, y = Ozone)) +
  geom_point() + 
  labs(title = "Temperature vs Ozone Levels",
       x = "Temperature (in Fahrenheit)",
       y = "Ozone (in ppb)")
```

The `ggplot()` function creates a blank canvas. The first argument specifies the dataset to use, and `aes()` sets the aesthetic mappings like the x and y variables. `geom_point()` adds the layer of points to our plot. Finally, `labs()` is used to add a title and labels for our axes.

### Box Plots with ggplot2

You can also create box plots with ggplot2. Here's the code that recreates our previous box plot with `boxplot()`:

```R
# box plot with ggplot2
ggplot(airquality, aes(x = Ozone)) +
  geom_boxplot(fill = "lightgreen") +
  labs(title = "Boxplot of Ozone Levels",
       x = "Ozone Levels",
       y = "Frequency")
```

Just like our scatter plot code, `geom_boxplot()` adds a box plot to our canvas. The `fill` argument in `geom_boxplot()` is used to fill the boxes with a light green color.

## Facets with ggplot2

A powerful feature of ggplot2 is the ability to add facets, or panels, to your plot. This allows you to create multiple plots at once, based on a specified factor variable.

Let's create a scatter plot of temperature vs ozone levels again. This time, however, we will create separate plots for each month in the year. To do this, we use `facet_wrap()`:

```R
# scatter plot with facets
ggplot(airquality, aes(x = Temp, y = Ozone)) +
  geom_point() +
  facet_wrap(~ Month) +
  labs(title = "Temperature vs Ozone Levels",
       x = "Temperature (in Fahrenheit)",
       y = "Ozone (in ppb)",
       subtitle = "Faceted by Month")
```

`facet_wrap()` creates facets arranged in a grid. Here, `~ Month` is a formula that specifies which variable to facet by. 

## Summary

In this lesson, we learned how to create simple plots like scatter plots, histograms, and box plots using base R and ggplot2 functions. We also learned how to customize plot appearance and how to use facets to create multiple condition-specific plots. Keep practicing your newfound plotting skills and exploring the wide range of plot types available in R! 

Our next lesson "Basic Statistics in R" will introduce you to basic statistical analyses and tests that you can perform with R. Join me in the next lesson to further extend your knowledge of air quality data analysis. 

[Continue to Lesson 6: Basic Statistics in R](./6-Basic-Statistics-in-R/readme.md)