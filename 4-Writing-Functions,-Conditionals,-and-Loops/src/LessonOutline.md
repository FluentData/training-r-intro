---
role: system
---
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


## Writing Functions, Conditionals, and Loops

Automate data tasks in R by writing reusable functions, conditional logic, and loops.

### Objectives

- Write custom functions in R
- Use if/else statements and for/while loops to control program flow
- Apply functions, conditionals, and loops to automate data processing tasks

### Topics

#### Writing functions

Syntax for defining custom functions in R.

##### Key Points

- Use fun <- function() {}
- Return values with return()

#### Function arguments

Adding arguments to functions.

##### Key Points

- Arguments passed to functions
- Use args=DEFAULT to make optional

#### Conditional statements

Using if/else logic to control code flow.

##### Key Points

- if(condition) {}
- else {} executed when condition FALSE
- Relational and logical operators

#### for loops

Repeating code through iterative loops.

##### Key Points

- for(var in vector) {}
- Iterates through elements

#### while loops

Repeating code while condition is true.

##### Key Points

- while(condition) {}
- Condition tested each iteration
- Avoid infinite loops

#### Applying functions and loops

Using custom functions and loops for data tasks.

##### Key Points

- Encapsulate repetitive tasks in functions
- Automate batch operations with loops

