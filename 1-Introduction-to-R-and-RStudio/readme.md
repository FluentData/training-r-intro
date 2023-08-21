# Introduction to R and RStudio

R is a programming language specialized for statistical analysis and data visualization. It was originally developed in academia, but it has since become widely used in industry and government. One of the main advantages of R is its open-source nature, which means that you can use it for free and that it has a large community of developers who constantly improve it and add new functionality. R's rich ecosystem of add-on packages will allow us to carry out complex data analysis tasks with a few commands.

## Table of Contents

1. [Why Use R?](#why-use-r-)
1. [Comparing R to Python for Data Science](#comparing-r-to-python-for-data-science)
1. [Installing R and RStudio](#installing-r-and-rstudio)
1. [Tour of the RStudio Interface](#tour-of-the-rstudio-interface)
1. [Wrapping up](#wrapping-up)

## Comparing R to Python for Data Science

Both R and Python are popular open-source languages for data science. While Python is a general-purpose language that can be used for many tasks beyond data analysis, R is a specialized language with a specific focus on statistics, data visualization, and data manipulation. This focus is particularly clear when looking at R's vast library of packages for statistical analysis. This does not mean that Python cannot do these tasks – it absolutely can, and very well – but R provides a more statistician-friendly environment. In this course, we will be diving deep into R's capabilities for air quality data analysis.

#### Exercise

List three reasons why someone might choose to use R over Python for data analysis.

<details><summary>Click for Hint</summary>

Consider the strengths of R mentioned in the section.

</details>
<details><summary>Click for Solution</summary>

1. R's specialization in statistics and data visualization.
2. R's extensive library of packages for statistical analysis.
3. R offers a more statistician-friendly environment.
      
> While both R and Python are powerful tools for data science, R's specific focus on statistical analysis and data visualization, its extensive library of packages, and its inherently statistician-friendly environment make it particularly appealing for projects heavily rooted in statistical analysis.
</details>

---

## Installing R and RStudio

To get started with R, you will need to install two pieces of software: R itself and the RStudio integrated development environment (IDE). The R software is what actually interprets and runs your R code, while RStudio provides a user-friendly interface that makes interacting with R much easier.

### 1. Install R

R can be installed from the Comprehensive R Archive Network (CRAN). Go to the [CRAN download page](https://cran.r-project.org/mirrors.html) and select a mirror that is close to your geographical location. Then click on the version of R for your operating system (Windows, Mac, Linux), and follow the instructions on the site to download and install R.

### 2. Install RStudio

Next, install RStudio. First, go to the [RStudio download page](https://www.rstudio.com/products/rstudio/download/#download). Under "Installers for Supported Platforms", click on the installer for your operating system and follow the instructions to download and install RStudio. 

Note: RStudio is not required for using R, but it makes it much easier to write and debug R code.

#### Exercise

Explain the roles of R and RStudio in the data analysis process.

<details><summary>Click for Hint</summary>

Think about the actual processing of the code and the environment in which you write and debug that code.

</details>
<details><summary>Click for Solution</summary>

R is the software that interprets and runs your code, while RStudio is a user-friendly interface that makes it easier to interact with R.
      
> R and RStudio provide two crucial components of the data analysis setup. R is the engine that runs your code, performing all of the operations and computations. RStudio, on the other hand, is the interface in which you write your code. It provides valuable features such as syntax highlighting, debugging tools, and project management, which can significantly enhance your coding experience and efficiency.
</details>

---

## Tour of the RStudio Interface

Once you have installed both R and RStudio, you can open RStudio to see the main interface, which is organized into four main “panes”:

1. The R Console (`bottom left by default`): This is where R is waiting for you to tell it what to do, and where it will show the results of the commands you run.
2. The Script pane (`top left by default`): This is where you can write longer pieces of code or create documents that mix text, code, and output.
3. The Environment/History pane (`top right by default`): Here, you can see a record of the commands you’ve previously entered and output you’ve previously computed (the “History” tab), as well as all the things you’ve defined and stored to use later (the “Environment” tab).
4. The Files/Plots/Packages/Help pane (`bottom right by default`): This pane has multiple uses, from browsing what files you’ve got in your current working directory (the “Files” tab), to seeing the plots you’ve made (the “Plots” tab), to getting some help on what different functions do (the “Help” tab). 

You can customize the layout of RStudio and the behavior of RStudio to suit your preferences. One common recommendation is to set RStudio to point to your project directory when you open a new session. Use the "Global Options…" in the Tools menu, then select "R General". In the "Default working directory (when not in a project)" you can browse and select your project directory. Click "Apply" and restart RStudio to see the changes.

To run any R command, simply type it into the console pane and hit `Enter`. For example, after typing `2 + 2` and hitting `Enter`, the console will show the result `4`.

This rudimentary command introduces us to the idea of R as a large, powerful calculator, and throughout this course we will incrementally build on that knowledge to harness the powerful statistical and data processing capabilities of the R programming language.

#### Exercise

Identify three features of the RStudio interface and describe their uses.

<details><summary>Click for Hint</summary>

Review the description of the four main panes in the RStudio interface.

</details>
<details><summary>Click for Solution</summary>

1. R Console: R waits here for input and displays results.
2. Script Pane: This is where you can write long pieces of code or documents.
3. Environment/History Pane: This shows a record of previous commands and stored variables.
      
> The RStudio interface is divided into four main parts, each with a specific purpose. The R Console is the command line interface where you can input commands and see the results. The Script Pane is akin to a text editor where you can write scripts or documents that are longer and more complex. Lastly, the Environment/History Pane allows you to see your command history and currently stored variables, aiding in project management and preventing repetition.
</details>

---

## Exercises

#### Exercise 1

Provide a step-by-step guide for someone on how to install R and RStudio on their computer.

<details><summary>Click for Hint</summary>

Steps for installing R and RStudio are mentioned in the 'Installing R and RStudio' section.

</details>
<details><summary>Click for Solution</summary>

1. Go to the CRAN download page and choose a mirror near your location.
2. Click on the version of R for your OS and follow the instructions to download and install R.
3. Go to the RStudio download page and under 'Installers for Supported Platforms', click on the installer for your OS and follow the instructions to download and install RStudio.
      
> Installing R and RStudio is a straightforward process. Visit the CRAN and RStudio websites, select the appropriate versions of their software for your OS, and follow the respective instructions provided. After a successful installation, you should be able to launch RStudio and begin your work in R.
</details>

---

#### Exercise 2

Write a short command in R to add two numbers.

<details><summary>Click for Hint</summary>

In R, you can simply use the '+' operator to add two numbers.

</details>
<details><summary>Click for Solution</summary>

2 + 3
      
> Using the '+' operator in R allows you to add two numbers together. The command '2 + 3' asks R to evaluate the sum of 2 and 3, which is 5.
</details>

---

#### Exercise 3

Explain the main differences between Python and R as tools for data analysis.

<details><summary>Click for Hint</summary>

Review the 'Comparing R to Python for Data Science' section in the material.

</details>
<details><summary>Click for Solution</summary>

While both are powerful tools for data analysis, Python is a general-purpose language suitable for a variety of tasks beyond just data analysis. R, in contrast, is specifically tailored towards statistics, data visualization, and data manipulation, offering a more statistician-friendly environment. Additionally, R's extensive package library, specifically for statistical analysis, is one of its core strengths.
      
> Python and R are both used in data analysis but differ in their scope and strengths. Python, being a general-purpose language, is ideal for various tasks beyond data analysis. On the other hand, R was specifically designed for statistics and data manipulation, and has a richer and more extensive package ecosystem suitable for data analysis, making it somewhat easier and more intuitive to use for statisticians and data scientists.
</details>

---

## Wrapping up

In this lesson, we introduced the R programming language for data analysis, the benefits of using a programming language such as R over traditional spreadsheet software, and a comparison of the relative strengths of R and Python for data science. We also covered installation of R and RStudio on personal computers and took a brief tour of the RStudio ecosystem.

----

In our upcoming [lesson](2-Functions-and-Data-Import/readme.md), we will delve deeper into functions and data import mechanisms in R!

