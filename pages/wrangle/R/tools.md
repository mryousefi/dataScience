---
layout: page
title: Wrangling Data
tagline: R Packages
---
{% include JB/setup %}


* dplyr
* [tidy](https://github.com/hadley/tidyr) - R package available on GitHub from Hadley Wickham to "tidy"-up data. The two main functions are 
	* `gather()` which "takes multiple columns, and gathers them into key-value pairs: it makes 'wide' data longer." 
	* `spread()` which "takes two columns (key & value) and spreads in to multiple columns, it makes 'long' data wider"
* [broom](https://github.com/dgrtwo/broom) - R package available on GitHub from David Robinson to take the output from built-in functions in R (e.g. estimated coefficients from `lm()`, `glm()`, `t.test()`, `anova()`) and convert it to a `tidy` data frame. Helpful to combine results from multiple models. 

## Resources 

