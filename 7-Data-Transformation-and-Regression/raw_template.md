# Data Transformation and Regression

Welcome back! In the previous lesson, we delved into basic statistical analysis using R. We calculated descriptive statistics, conducted hypothesis tests, and even fit basic linear models. Now, using those foundational skills, we kick things up a notch. Get ready to dive into the heart of data preprocessing and regression modeling!

## Data Transformations 

Data transformations are a ubiquitous method in statistical analysis including air quality data. They help to stabilize variance, make the data more closely align with the assumptions of the inferential model, and improve interpretability. 

### Log, Square root & Box-Cox

For measurements that are skewed, we may apply transformations to reexpress our data for improved analysis. For instance, air pollutant data is often skewed right because it cannot go below zero, but there can be some very high values during pollution events.

Let's import our air quality data and try out some transformations.
  
```R
# Import the data
data <- read.csv("./data/chicago_air.csv")

# Apply a square root transformation
data$sqrt_ozone <- sqrt(data$ozone)

# Apply a log transformation
data$log_ozone <- log(data$ozone)

# Use the boxcox() function to do a Box-Cox transformation
library(MASS)  # boxcox() is in MASS package
data$bc_ozone <- boxcox(data$ozone ~ 1, lambda = seq(-0.5, 0.5, by=0.1))
``` 

The log, square root and Box-Cox are common transformations when dealing with skewed data. Note that Box-Cox is a family of transformations and requires us to choose a 'lambda' parameter that determines the specific transformation to apply.

## Regression Analysis 

We've previously built a simple linear model. It's now time to take it up a notch and bring our new skills together. 

### Simple Linear Regression Model 

Just to refresh, here's how you would build a simple linear model of the relationship of temperature with the ozone.

```R
# Fit the model
model <- lm(ozone ~ temp, data = data)

# Model summary
summary(model)
```

This tells us if there's a statistically significant linear relationship between temperature and ground level ozone concentration. 

### Confidence Intervals 

While summarizing the model will give us coefficient estimates, we can also compute their confidence intervals using the `confint()` function.

```R
# Confidence intervals for model coefficients
confint(model)
```

## Missing Data 

Real-world air quality data often contains missing values, referred to as NAs in R. Before doing many operations in R, we usually need to handle these.

### Handling Missing Values 

```R
# Total number of NAs in dataset
sum(is.na(data$ozone))

# Remove rows with NA values
data <- na.omit(data)

# Check if NAs are removed
sum(is.na(data$ozone))
```

## Outliers 

Finally, let's discuss outliers in our data. Outliers can greatly affect our analysis, especially models because they can lead to erroneous conclusions. 

### Identifying and Handling Outliers

Let's use boxplots to identify potential outliers in our dataset. Boxplots represent the median (middle line), first and third quartiles (box), and the range (whiskers). Outliers are shown as individual points outside the whiskers.

```R
# Create a boxplot
boxplot(data$ozone, main = "Boxplot of Ozone levels", ylab = "Ozone (ppm)", col = "blue")
```
If outliers are found, you could consider removing them, winsorizing the data (replacing outliers with less extreme values), or use robust statistical methods designed to be not too badly affected by outliers.

## Wrapping up

In this lesson, we dove deep into the world of data pre-processing before regression analysis, including important topics like data transformations, regression modeling, handling missing data and outliers. All of these make up key steps for accurately interpreting real-world air quality data. 

**[Up Next](../8-quality-assurance/readme.tmd)**: As we near the end of this introductory R course, we will look at ensuring the quality of our data and output. Remember, there will always be garbage-in, garbage-out phenomenon in data science, to get quality output, you need to ensure the quality of the input. Head on over to the next lesson where we will learn techniques to assess and improve data quality!