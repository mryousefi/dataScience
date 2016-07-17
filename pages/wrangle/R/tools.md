---
layout: page
title: Wrangling Data
tagline: R Packages
---
{% include JB/setup %}

## dplyr
[dplyr[(https://github.com/hadley/dplyr) - Transforms and summarizes tabular data with rows and columns. Contains a set of functions (or "verbs") to perform common data manipulation operations such as filtering for rows, selecting specific columns, re-ordering rows, adding new columns and summarizing data. In addition, dplyr contains a useful function to perform another common task which is the is the "split-apply-combine" concept.  

Basic dplyr verbs | Description
--- | ---
`select()` | select columns 
`filter()` | filter rows
`arrange()` | re-order or arrange rows
`mutate()` | create new columns
`summarise()` | summarise values
`group_by()` | allows for group operations in the "split-apply-combine" concept

#### Pipe operator
The pipe operator (%>%) is imported by dplyr from another package (magrittr).  This operator allows you to pipe the output from one function to the input of another function.  Instead of nesting functions (reading from the inside to the outside), the idea of of piping is to read the functions from left to right. libsdf

## tidyr
[tidyr](https://github.com/hadley/tidyr) - Makes the tabular data "tidy" by converting it between a "wide" and "long" format. 
> library(tidy)
> df = data.frame("geneName" = paste("gene", 1:5, sep="_"), "control" = rnbinom(5, size = 0.5,  mu = 1000), 
> 				"treatment" = rnbinom(5, size = 0.5, mu = 100))
> 
> # converts "wide" data into "long" data; Uses multiple columns as input and gathers them into key-value pairs
> # Provide the names of key/value columns to create: `status` = control/treatment status, `geneExpression` = level of gene expression 
> df_long = df %>% gather(status, geneExpression, -geneName) # similar to melt() in reshape2
> 
> # converts "long" data into "wide" data; complement of `gather()`; probably will use less frequently than `gather()`
> # Provide the column names that represent the key and value pairs
> df_long %>% spread(tsatus, geneExpression) # similar to cast() in reshape2
> 
> # separates one column into multiple columns based on a position or pattern
> # Provide `col` (the column to split), `into` (a vector of character strings representing the new column names and the separator), and `extra` (what to do with the extra columns if the data doesn?t split nicely). 
> df %>% separate(geneName, c("gene", "geneNumber")) 

#### broom
[broom](https://github.com/dgrtwo/broom) - Converts output from built-in functions in R (e.g. estimated coefficients from `lm()`, `glm()`, `t.test()`, `anova()`) to a `tidy` data frame. Helpful to combine results from multiple models. 
> library(broom)
> # Summarizes the statistical findings
> # The following two lines produce the same result: the first nests the functions and the second uses the pipe operator. 
> tidy(t.test(df$control, df$treatment))
> df_long %>% t.test(geneExpression ~ status, .) %>% tidy()

Two other functions:
	* `augment()` = includes other results (e.g. predictions & residuals from fitting linear models)
	* `glance()` = concise one-row summary of the model

## Resources 

