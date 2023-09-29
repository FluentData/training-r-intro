---
role: system
---
## Introduction to R and RStudio

Get started with R and RStudio by learning how to run basic commands, assign variables, and work with data structures.

### Objectives

- Install and setup R and RStudio
- Understand core R concepts like variables, data types, vectors, lists, matrices, data frames

### Topics

#### What is R?

Overview of R as a programming language for data analysis. Brief history.

##### Key Points

- R is a programming language specialized for statistical analysis and visualization
- Originated in academia but now widely used in industry/government
- Open source tool with thousands of add-on packages

#### Why use R?

Discuss advantages of R over spreadsheets/BI tools for custom analysis.

##### Key Points

- Flexibility for doing custom data science/modeling beyond canned reports
- Reproducibility by using RScripts instead of click-based GUIs
- Large collection of specialized packages for data tasks

#### R vs python

Compare R to python for data science.

##### Key Points

- Both are popular open source languages for data science
- R is more specialized for statistical analysis
- Python is more general purpose

#### Installing R and RStudio

Downloading and installing R and RStudio IDE.

##### Key Points

- Download base R from CRAN repository
- Download RStudio IDE which provides nice interface
- Walk through installation process

#### RStudio IDE overview

Tour of the RStudio interface and panes. Setting working directory.

##### Key Points

- Explain the purpose of each pane
- Setting working directory to organize projects
- Keyboard shortcuts to navigate panes


## Functions and Data Import

Learn how to use functions in R and import data from common sources like CSVs and Excel.

### Objectives

- Understand what functions are and how to use them
- Use built-in R functions like mean(), paste(), seq()
- Install and load R packages
- Import CSV and Excel data into R

### Topics

#### Functions in R

Definition of a function in R. Using functions with arguments.

##### Key Points

- Functions encapsulate reusable code
- Call functions with name(arguments)
- Arguments provide data/configuration

#### Built-in R functions

Examples of common built-in functions like mean(), paste(), seq()

##### Key Points

- mean() for calculating averages
- paste() for concatenating text
- seq() for generating sequences

#### Nesting functions

Placing functions inside other functions.

##### Key Points

- Functions can call other functions
- Innermost functions execute first

#### R packages

Installing packages from CRAN. Loading with library().

##### Key Points

- Packages extend R's capabilities
- Use install.packages() to install
- Use library() to load installed packages

#### Importing data

Reading CSVs with read.csv(). Reading Excel with readxl package.

##### Key Points

- read.csv() to import CSV data
- Install/load readxl package for Excel imports
- Set options like stringsAsFactors, na.strings

