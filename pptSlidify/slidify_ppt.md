---
title       : Developing Data Products
subtitle    : Select the best car for your trip!!
author      : Arpita Jena
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

INTRODUCTION

This presentation is part of the Course Project for the Coursera Developing Data Products class. The peer assessed assignment has two parts. First, we need to create a Shiny application and deploy it on Rstudio's servers. Second, we should use Slidify or Rstudio Presenter to prepare a reproducible pitch presentation about the application. This presentation adresses the second part of the course project.

1. The app developed for the first part of the assignment is avalilable at:
[app_url](https://arpitajena.shinyapps.io/shiny_app/)

2. Source code for ui.R and server.R files are available on the GitHub:
[source_code](https://github.com/arpitajena1990/developing_data_products)

---

SELECT THE BEST CAR FOR YOUR TRIP APP

This app helps you to choose a car for a trip, using the mtcars dataset from [R].
> 1. You need to inform the distance of your trip and the price of gasoline in your region. These information will be used to calculate the Gasoline Expenditure for each car in the dataset. Then, you can enter the maximum amount of money you want to spend on gasoline, and the table shows only the cars that have Miles per Gallon (mpg) that can go below this value.
> 2. You can choose some caractheristcs of the cars that you desire: Cylinders, Displacement, Gross Horse Power and Transmission. The table will show only the cars with the filters selected. You can sort the table according to the variable you want by clicking the arrows at the top of the table.

---

MTCARS DATASET

The data used in the app comes from the Motor Trend Car Road Tests (mtcars) dataset. The data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973-74 models). We can look to some carachteristics of the data as given below:

```r
head(mtcars)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

---

PLOT

Here we can see the relationship between three variables: miles per gallon (mpg), displacement (disp) and weight (wt).

```r
library(car)
```

```
## Warning: package 'car' was built under R version 3.2.5
```

```r
scatterplot.matrix(~mpg+disp+wt, data=mtcars, cex.axis=1.5)
```

```
## Warning: 'scatterplot.matrix' is deprecated.
## Use 'scatterplotMatrix' instead.
## See help("Deprecated") and help("car-deprecated").
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)
