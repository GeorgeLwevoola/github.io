---
title       : Shiny Project Example
subtitle    : Prediction Algorithm
author      : George Lwevoola
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## 1. Introduction

This Shiny application demonstrates the use of a web-based Client-Server
Model to create reproducible prediction models. 

The goal of this project is to predict the manner in which 20 subjects performed exercise (how well). 

This is represented by the "classe" variable in the training data set.

The data used for this sample application is derived from the Practical Machine Learning module.

--- .class #id 

## 2. Dataset selection
The training dataset is located at https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv 

while the test data set on which the prediction model will be used is at
https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv

This data has been cleaned up and for this sample application is represented as

1. Training data set - mytrainfile.csv
2. Test data set - my testfile.csv


---
## 3. Machine Learning Algorithms
Three machine learning algorithms have been selected for the sample application

1. Linear Discriminant Analysis (LDA)

2. Random Forest (rf)

3. Recursive Partitioning and Regression Trees (rpart)

Random Forest yields the most accurate prediction and used as an example

---
## 4. Displaying Results
Using the application involves selecting from a drop down list.

Below we use the Random Forest algorithm as an example


The Prediction for the selected algorithm is calculated and displayed

```r
predict(fit.rf,testing)
```

```
##  [1] B A B A A E D D A A B C B A E E A B A B
## Levels: A B C D E
```

The display also includes the accuracy of algorithm selected


```r
round(rf.accuracy$overall,3)
```

```
##       Accuracy          Kappa  AccuracyLower  AccuracyUpper   AccuracyNull 
##          0.941          0.925          0.925          0.955          0.284 
## AccuracyPValue  McnemarPValue 
##          0.000            NaN
```

