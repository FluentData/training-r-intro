---
role: system
---
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


## Subsetting, Sorting, and Combining Data

Learn techniques for selecting, ordering, and joining datasets in R.

### Objectives

- Subset data frames using indexing, logical operators, filter()
- Sort data frames with arrange()
- Combine data frames together with bind_rows()

### Topics

#### Viewing Data Frames

Using head(), tail(), and View() to inspect data frames.

##### Key Points

- head() shows first 6 rows
- tail() shows last 6 rows
- View() opens data viewer

#### Subsetting

Selecting data subsets using [], $, filter().

##### Key Points

- [row,col] extracts elements
- $ extracts named columns
- filter() subsets rows

#### Sorting

Ordering rows with arrange() and desc().

##### Key Points

- arrange() sorts rows
- desc() sorts in descending order

#### Combining

Appending data frames together with bind_rows().

##### Key Points

- bind_rows() stacks data frames
- Useful for joining related datasets

