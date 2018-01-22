# pkgreviewr

The goal of pkgreviewr is to facilitate **rOpenSci** package reviews.

## Installation

You can install pkgreviewr from GitHub with:


``` r
# install.packages("devtools")
devtools::install_github("annakrystalli/pkgreviewr")
```

## Example

### create review project

This is a basic example which shows you how to solve a common problem:


First, create the review project, using `pkgreview_create`. The function takes arguments `pkg_repo`, the repo details in the form `username/repo` and `review_dir`,
the directory in which the review project will be created.

The functions creates a new review project (or prompts for instruction if it already exists) and navigates to the project root.

``` r
library(pkgreviewr)
pkgreview_create(pkg_repo = "cboettig/rdflib", 
                 review_dir = "~/Documents/workflows/rOpenSci/reviews/")
```

### initialise review

Next, initialise the review project with the materials you'll need.

``` r
library(pkgreviewr)
pkgreview_init("cboettig/rdflib")

```
![](inst/assets/proj_structure.png)

<br>

The most important file it creates `index.Rmd html_notebook` file. This workbook is prepopulated with all the major steps required to complete the review in an interactive document to perform and record it in. It also extracts useful links, information and parameter values. See example [here](https://github.com/annakrystalli/pkgreviewr/blob/master/inst/examples/example-review-index.Rmd)

Once rendered to `index.nb.html`, this report can be pushed to github for publication which needs to be pushed to github for the report

Initialisation also clones package source code from github to a second new directory, in the same directory and depth as the review project.

