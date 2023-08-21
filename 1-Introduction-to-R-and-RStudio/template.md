Welcome to the first lesson of our R for Air Quality Data Science
training course! In this lesson, we will introduce you to the R
programming language and the RStudio integrated development environment.
We will look at how to install these tools on your own computer and
familiarize yourself with the environment where you will be doing most
of your R programming.

By the end of this lesson, you will be able to: 1. Install and setup R
and RStudio. 2. Understand core R concepts like variables, data types,
vectors, lists, matrices, and data frames.

Why Use R?
----------

R is a programming language specialized for statistical analysis and
data visualization. It was originally developed in academia, but it has
since become widely used in industry and government. One of the main
advantages of R is its open-source nature, which means that you can use
it for free and that it has a large community of developers who
constantly improve it and add new functionality. R’s rich ecosystem of
add-on packages will allow us to carry out complex data analysis tasks
with a few commands.

Comparing R to Python for Data Science
--------------------------------------

Both R and Python are popular open-source languages for data science.
While Python is a general-purpose language that can be used for many
tasks beyond data analysis, R is a specialized language with a specific
focus on statistics, data visualization, and data manipulation. This
focus is particularly clear when looking at R’s vast library of packages
for statistical analysis. This does not mean that Python cannot do these
tasks – it absolutely can, and very well – but R provides a more
statistician-friendly environment. In this course, we will be diving
deep into R’s capabilities for air quality data analysis.

Installing R and RStudio
------------------------

To get started with R, you will need to install two pieces of software:
R itself and the RStudio integrated development environment (IDE). The R
software is what actually interprets and runs your R code, while RStudio
provides a user-friendly interface that makes interacting with R much
easier.

### 1. Install R

R can be installed from the Comprehensive R Archive Network (CRAN). Go
to the [CRAN download page](https://cran.r-project.org/mirrors.html) and
select a mirror that is close to your geographical location. Then click
on the version of R for your operating system (Windows, Mac, Linux), and
follow the instructions on the site to download and install R.

### 2. Install RStudio

Next, install RStudio. First, go to the [RStudio download
page](https://www.rstudio.com/products/rstudio/download/#download).
Under “Installers for Supported Platforms”, click on the installer for
your operating system and follow the instructions to download and
install RStudio.

Note: RStudio is not required for using R, but it makes it much easier
to write and debug R code.

Tour of the RStudio Interface
-----------------------------

Once you have installed both R and RStudio, you can open RStudio to see
the main interface, which is organized into four main “panes”:

1.  The R Console (`bottom left by default`): This is where R is waiting
    for you to tell it what to do, and where it will show the results of
    the commands you run.
2.  The Script pane (`top left by default`): This is where you can write
    longer pieces of code or create documents that mix text, code, and
    output.
3.  The Environment/History pane (`top right by default`): Here, you can
    see a record of the commands you’ve previously entered and output
    you’ve previously computed (the “History” tab), as well as all the
    things you’ve defined and stored to use later (the “Environment”
    tab).
4.  The Files/Plots/Packages/Help pane (`bottom right by default`): This
    pane has multiple uses, from browsing what files you’ve got in your
    current working directory (the “Files” tab), to seeing the plots
    you’ve made (the “Plots” tab), to getting some help on what
    different functions do (the “Help” tab).

You can customize the layout of RStudio and the behavior of RStudio to
suit your preferences. One common recommendation is to set RStudio to
point to your project directory when you open a new session. Use the
“Global Options…” in the Tools menu, then select “R General”. In the
“Default working directory (when not in a project)” you can browse and
select your project directory. Click “Apply” and restart RStudio to see
the changes.

    # This is a simple calculation example executed in R
    2 + 2

    ## [1] 4

This rudimentary command introduces us to the idea of R as a large,
powerful calculator, and throughout this course we will incrementally
build on that knowledge to harness the powerful statistical and data
processing capabilities of the R programming language.

Wrapping up
-----------

In this lesson, we introduced the R programming language for data
analysis, the benefits of using a programming language such as R over
traditional spreadsheet software, and a comparison of the relative
strengths of R and Python for data science. We also covered installation
of R and RStudio on personal computers and took a brief tour of the
RStudio ecosystem.

------------------------------------------------------------------------

In our upcoming [lesson](2-Functions-and-Data-Import/readme.md), we will
delve deeper into functions and data import mechanisms in R!
