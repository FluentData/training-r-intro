# Plotting with ggplot2

In our [last lesson](../4-Writing-Functions-Conditionals-and-Loops), we finished automating our data processing tasks using functions, conditionals, and loops. Now we are ready to explore and understand our data better with visualizations. 

## Introduction to ggplot()

`ggplot2` is a powerful and flexible data visualization package in R. It uses a layered approach to plot building, which allows you to add, remove or change components in a straightforward, transparent manner. 

To use `ggplot2`, we typically follow a sequence of steps:

1. Start with the `ggplot()` function where we specify the dataset and map variables to aesthetics (visual properties of objects in the plot like shapes or colors).
2. Add `geoms` – geometric objects like points (`geom_point` for scatter plots), bars (`geom_bar` for bar plots), or lines (`geom_line` for line plots) that determine the type of the plot.
3. Finally, customize and refine the plot with additional layers like labels, themes, facets etc.

Let's begin by installing and loading the `ggplot2` package. If you haven't installed it before, uncomment and run the first line.

```r
# install.packages('ggplot2')
library(ggplot2)
```

Now we are ready to use `ggplot2` to make some plots!

## Scatter Plot

For our first plot, let's create a scatter plot of ozone concentration (`ozone`) against temperature (`temp`) using the `chicago_air.csv` dataset. 

```r
# Load the dataset
air_quality <- read.csv('../data/chicago_air.csv')

# Create a scatter plot
ggplot(air_quality, aes(x=temp, y=ozone)) +
  geom_point()
```

In this example, we have used `geom_point()` to create a scatter plot. The first argument to `ggplot()` function is the dataset `air_quality`. The `aes()` function is used to map the `temp` to x-axis and `ozone` to y-axis.

## Customizing the Scatter Plot

The plot above is pretty basic. Let's customize it by adding color, title and labels.

```r
# Customized scatter plot
ggplot(air_quality, aes(x=temp, y=ozone)) +
  geom_point(colour='#3366FF') +
  ggtitle('Relationship between Ozone and Temperature') +
  xlab('Temperature (°F)') +
  ylab('Ozone (ppm)')
```

Here we used `geom_point(colour='#3366FF')` to change the point color, `ggtitle()` to add a title to the plot and `xlab()` & `ylab()` to label the x and y axes respectively.

## Histogram

Next, let's create a histogram of `ozone` concentrations.

```r
# Histogram
ggplot(air_quality, aes(x=ozone)) +
  geom_histogram(binwidth=0.005, fill='#FF6633', color='black')
```

Histogram divides the continuous variable into bins (intervals) and count the number of observations in each bin. So unlike scatter plot, histogram only needs one variable (`ozone` in this case) which is passed to x. The `binwidth` argument controls the width of the bins and `fill` changes the color of the bars.

## Faceted Bar Plot

Lastly, let's create a bar plot showing the average `ozone` concentration for each `month`, and facet it by `weekday`.

First, we need to calculate the average `ozone` concentration per `month` and `weekday`. We will use `aggregate()` function from base R for this purpose.

```r
# Calculate mean ozone concentration per month and weekday
avg_ozone <- aggregate(ozone ~ month + weekday, data = air_quality, FUN = mean, na.rm = TRUE)

# Create faceted bar plot
ggplot(avg_ozone, aes(x=month, y=ozone, fill=weekday)) +
  geom_bar(stat='identity') +
  theme_minimal() +
  facet_wrap(~weekday) +
  labs(title='Average Ozone Concentration per Month, Faceted by Weekday',
       x='Month',
       y='Average Ozone Concentration (ppm)')
```

Here we are using `geom_bar(stat='identity')` to create a bar plot. The `facet_wrap()` function creates a series of plots for each level of `weekday` factor. The `theme_minimal()` gives a clean white background.

## Up Next

In this lesson, we used `ggplot2` to create and customize a variety of graphics. We covered the basics of the `ggplot()` function structure, and we practiced creating scatter plots, histograms, and bar plots, and learned how to facet our plots.

In our [next lesson](../6-Basic-Statistics-in-R), we will move into calculating common descriptive and inferential statistics such as mean, median, correlation, confidence intervals, t-tests, ANOVA, and linear models. We will use these statistical tools to continue exploring and gaining insights from our air quality datasets!