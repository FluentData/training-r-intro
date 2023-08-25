# Plotting with R

In our previous lesson, [Writing Functions, Conditionals, and Loops](./4-Writing-Functions-Conditionals-and-Loops/readme.md), we automated repetitive tasks and controlled the workflow of our R programming. Today we are going to shift towards an extremely important aspect of data analysis: data visualization. Creating comprehensive and informative visualizations brings data to life, revealing patterns and trends in data that are not immediately obvious from raw numbers. R offers a broad range of functions for creating various types of plots and gives you the control to customize them according to your needs.

## Objectives

By the end of this lesson, you will be able to:

- Recognize the importance of data visualization
- Create basic plots like scatter plots, line plots, box plots, and histograms using base R functions
- Fine-tune and customize appearances of plots
- Understand and use ggplot2 for enhanced plotting capabilities
- Generate multiple mini-abstracts of plots using facets

## Data Visualization: An Integral Part of Data Analysis

Data visualization is one of the most powerful tools at a data analyst's disposal. Through different plot types, charts, and graphs, an analyst can illustrate trends, patterns, outliers, and much more. Not only do these visuals help in extracting insights from the data but they are also essential for communicating findings effectively.

One of the beauties of R is the wide variety of packages for creating and customizing high-quality plots. Two of the most commonly used for this purpose are base R graph functions and ggplot2. We will be exploring both of these in our lesson today, building onto our data manipulation skills.

## Base R Plots

Base R comes equipped with several functions for data visualizations. Let's start with basic functions to create line plots, scatter plots, box plots, bar plots, density plots, and histograms. 

To set the foundation, we will begin with simple examples, continue to add complexity, and customize as we delve deeper into the lesson.

### Scatter Plots with plot()

We initiate our visual exploration by creating a scatter plot. For this exercise, we will be using the `airquality` dataset pre-built in R. This dataset holds air quality measurements of New York.

```R
data(airquality)
head(airquality)

plot(airquality$Temp, airquality$Ozone, 
     main = "Temperature vs Ozone Levels", 
     xlab = "Temperature (in Fahrenheit)", 
     ylab = "Ozone (in ppb)")
```

Here, the `plot()` function is utilized. This function is quite versatile and by default it plots a scatter graph. The first two arguments represent x and y variables, while the 'main', 'xlab', and 'ylab' are the title of the graph, the label for the x-axis, and the label for y-axis, respectively. 

Common argument variations include:
- `type` can define the type of plot e.g. line ('l'), point ('p'), or both ('b') 
- `pch` to adjust the shape of the scatter points
- `col` to change color of the points 
- `xlim` and `ylim` to set limits on x and y axis respectively

(Please add bar plots and density plots examples)

### Histograms with hist()

Histograms are excellent tools for visualizing the distribution of a single numerical variable. We transform this numerical variable into several bins and count the number of occurrences in each bin. In the following example, we use `hist()` to construct a histogram of wind speeds extracted from the `chicago_wind.csv` dataset.

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

The `col` argument fills the bars with a light blue color.

Common argument variations include: 
- `breaks` defines bin widths
- `freq` toggles between frequency(`TRUE`) and density(`FALSE`) on y-axis
- `xlim` and `ylim` to set limits on x and y axis respectively

(Please add examples of line plots and box plots)

## Introduction to ggplot2

While base R provides a range of functions for creating plots, there are packages like `ggplot2` which are more powerful and provide better control over features. Part of the `tidyverse` suite of packages, ggplot2 is a favorite among R users for creating complex multi-layered visualizations with simple syntax.

Before we discuss further, here is a quick `ggplot2` installation and loading guide if you don't have it already.

```R
install.packages("ggplot2") # Required only once
library(ggplot2)            # Required in every new session
```

One of the distinct principles of ggplot2 is the use of aesthetics(`aes()`). Aesthetic mappings dictate how variables in your data are mapped to visual properties (aesthetics) of the plot. For example, if we specifically want to map data to x and y coordinates, we utilize the`aes(x = , y = )`.

So, once loaded, we can easily recreate our precious plots using `ggplot()` function.

```R
ggplot(airquality, aes(x = Temp, y = Ozone)) +
  geom_point() + 
  labs(title = "Temperature vs Ozone Levels",
       x = "Temperature (in Fahrenheit)",
       y = "Ozone (in ppb)")
```

The `ggplot()` function sets up a flexible canvas to which we can add, or overlay, different types of graphs as layers. The `aes()` function sets the `x` and `y` variables, `geom_point()` function creates a layer of points(aka scatter plot). Lastly, `labs()` function is accountable for adding labels and title to our graph.

(Please add remainder of the plot examples, continue building on the plots and explaining how `facet_wrap()` or `facet_grid()` are used to create facets in ggplot2)

## Summary

Today we dove deeper into one of R's prominent applications - Data Visualization. We explored the basics of plotting with Base R and ggplot2, and the respective capabilities of both. We learned that base R offers straightforward syntax for simple graphs, but to truly tap into the potential of visualizations, ggplot2 is indispensable.

In the next lesson, we will be extending our understanding of air quality data analysis and uncovering more insights by learning about "Basic Statistics in R". Curious about the story our air quality data holds? Join me in the next lesson where we will peel the layers of this narrative.




[Continue to Lesson 6: Basic Statistics in R](./6-Basic-Statistics-in-R/readme.md) 
