---
title       : evaluatr
subtitle    : a text evaluation program
author      : Sean C. Rife, Ph.D.
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## the problem

* Unstructured text data is everywhere
  * Facebook
  * Twitter
  * Blogs
  * Message boards
* Analyzing these data using traditional quantitative methods (correlation, regression, etc.) is impossible without some intermediary transformation
* Existing solutions (e.g., sentiment analysis, word counts) provide only limited insights into the meaning of a body of text

---
## solution: the LIWC framework

* LIWC (pronounced "Luke") is a framework for extracting the psychological meaning of words
 * Developed by Pennebaker (2000) through a factor analysis of large existing bodies of text
  * More information available from http://www.liwc.net and http://bit.ly/NirLSc
* LIWC uses a dictionary to rate a body of text in 63 categories. Examples:
  * Insight
  * Work
  * Money
  * Death
  * Social processes

---
## evaluatr: applying the LIWC framework and dictionary

* evaluatr applies the LIWC framework and English dictionary to provide an analysis of entered text
* Source code available from:
  * http://www.github.com/seanrife/evaluatr (full Shiny app)
  * http://www.github.com/seanrife/liwcr (LIWC implementation in R)
* LIWC dictionaries are proprietary and must be purchased (along with standalone software for Windows or Macintosh) from http://www.liwc.net

---
## Example
* The evaluatr program uses the liwcr package (soon to be submitted to CRAN) to provide a web-based implementation of LIWC
* The liwcr program takes two arguments: the text to be analyzed, and the dictionary for the analysis. Example:

```r
source("liwcr.R")
```

```r
liwcr("I love writing code all the time, day and night. Especially night.", "eng.dic")[3:7,]
```

```
##   V1    V2 count percent
## 3  3 ppron     1   8.333
## 4  4     i     1   8.333
## 5  5    we     0   0.000
## 6  6   you     0   0.000
## 7  7 shehe     0   0.000
```
(Note: the bracketed "3:7" limits the number of rows displayed for this presentation.)
