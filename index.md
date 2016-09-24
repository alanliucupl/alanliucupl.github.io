---
title       : Predicting Childrens' Height
subtitle    : Developing Data Products Deck
author      : JL
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Overview

This deck aims to research on the impact of parents' heights and children's gender on the children's heights.

--- .class #id 

## Source Data and Tools

Source Data: dataset GaltonFamilies in the HistData R package

Tools: shiny to build data product application and slidify to create decks

--- .class #id 

## Data


```r
library(HistData)
data(GaltonFamilies)
summary(GaltonFamilies)
```

```
##      family        father         mother      midparentHeight
##  185    : 15   Min.   :62.0   Min.   :58.00   Min.   :64.40  
##  066    : 11   1st Qu.:68.0   1st Qu.:63.00   1st Qu.:68.14  
##  120    : 11   Median :69.0   Median :64.00   Median :69.25  
##  130    : 11   Mean   :69.2   Mean   :64.09   Mean   :69.21  
##  166    : 11   3rd Qu.:71.0   3rd Qu.:65.88   3rd Qu.:70.14  
##  097    : 10   Max.   :78.5   Max.   :70.50   Max.   :75.43  
##  (Other):865                                                 
##     children         childNum         gender     childHeight   
##  Min.   : 1.000   Min.   : 1.000   female:453   Min.   :56.00  
##  1st Qu.: 4.000   1st Qu.: 2.000   male  :481   1st Qu.:64.00  
##  Median : 6.000   Median : 3.000                Median :66.50  
##  Mean   : 6.171   Mean   : 3.586                Mean   :66.75  
##  3rd Qu.: 8.000   3rd Qu.: 5.000                3rd Qu.:69.70  
##  Max.   :15.000   Max.   :15.000                Max.   :79.00  
## 
```

--- .class #id 

## Model


```r
lm(childHeight ~ father + mother + gender, data=GaltonFamilies)
```

```
## 
## Call:
## lm(formula = childHeight ~ father + mother + gender, data = GaltonFamilies)
## 
## Coefficients:
## (Intercept)       father       mother   gendermale  
##     16.5212       0.3928       0.3176       5.2150
```

--- .class #id 

## Application

To show the impact of parents' height and children' gender, an application has been developed and deployed at https://jiayuliu.shinyapps.io/shiny_apps_1/.


--- .class #id 

