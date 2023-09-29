---
role: system
---
## Basic Statistics in R

Calculate common descriptive and inference statistics in R.

### Objectives

- Calculate summary statistics like mean, median, correlation
- Generate confidence intervals and perform t-tests
- Perform ANOVA analysis and linear models

### Topics

#### Summary statistics

Functions for descriptive stats like mean(), median().

##### Key Points

- mean(), median() for central tendency
- sd(), var() for spread
- cor() for correlation

#### Confidence intervals

Using t.test() for intervals and inference.

##### Key Points

- t.test() for confidence intervals
- Outputs p-value for significance

#### ANOVA

One-way ANOVA analysis with aov() and TukeyHSD().

##### Key Points

- aov() fits ANOVA model
- TukeyHSD() for post-hoc tests

#### Linear models

Fitting linear models with lm().

##### Key Points

- lm() fits linear regression models
- summary() to view model output


## Data Transformation and Regression

Transforming variables and building regression models.

### Objectives

- Transform variables using standard transformations
- Perform basic regression analysis and inference
- Handle missing data and outliers

### Topics

#### Transformations

Common transformations like log, square root, box-cox.

##### Key Points

- log(), sqrt(), boxcox()
- Normalizing skewed data

#### Simple regression

Linear models using lm().

##### Key Points

- lm(y~x) formula syntax
- summary() to view model stats
- confint() for confidence intervals

#### Missing data

Dealing with NA values.

##### Key Points

- NA represents missing data
- [object Object]
- [object Object]

#### Outliers

Identifying and handling outliers.

##### Key Points

- Check for outliers in plots, statistics
- Remove extreme outliers
- Robust modeling approaches

