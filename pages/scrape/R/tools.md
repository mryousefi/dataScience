---
layout: page
title: Scraping Data
tagline: R Packages
---
{% include JB/setup %}


#### Opens URLs or Interacts with APIs
* [httr](http://cran.r-project.org/web/packages/httr/index.html) - wrapper for Rcurl to work with web APIs. 
* [jsonlite](http://cran.r-project.org/web/packages/jsonlite/index.html) - Parse JSON-formatted data and interact with web APIs. Started out as a forked version of [RJSONIO](http://cran.r-project.org/web/packages/RJSONIO/index.html), but is now completely re-written. 
* [Rcurl](http://cran.r-project.org/web/packages/RCurl/index.html) - Fetches URLs and parses results 
* [RSelenium](http://cran.r-project.org/package=RSelenium) - Interface with the Selenium Webdriver API

#### Parses HTML/XML
* [rvest](https://github.com/hadley/rvest) - Parse html pages from web and use data in R. Inspired from the python modules [Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/) and [RoboBrowser](http://robobrowser.readthedocs.org/en/latest/readme.html). 
* [XML](http://cran.r-project.org/web/packages/XML/index.html) and  [XML2R](https://github.com/cpsievert/XML2R) - Parse and generate XML pages

#### Reads in specific files
> read.table("myTextFile.txt", header = TRUE) # reads in text files
> read.csv("myCSVFile.csv", header = TRUE, sep = ",") # reads in CSV files

* [readxl](https://github.com/hadley/readxl) - Reads in `.xls` and `.xlsx` files. 
> library(readxl)
> excel_sheets("myExcelFile.xlsx") # lists all sheets in file
> read_excel("myExcelFile.xlsx'" sheet = 1, col_names = TRUE, skip = 0) # reads in sheet 1 in file
By default, blank cels are converted to missing values. 

* 

#### R packages to scrape data
* [bbscrapeR](https://github.com/cpsievert/bbscrapeR) - R package for collecting NBA play-by-play, shot location, and some Sport VU data.


## Resources 

* [Slides on Web scraping in R from Carson Sievert](http://cpsievert.github.io/slides/web-scraping/)
* [Cool example on extracting images from html pages using Rcurl + httr + XML](http://www.r-bloggers.com/the-average-stripe-employee-congrats-to-alyssa/)
