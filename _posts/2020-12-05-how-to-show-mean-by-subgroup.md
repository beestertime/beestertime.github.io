---
layout: post
title: "3. Stata: How to show mean/median by subgroup"
description: "How to show mean/median by subgroup"
keywords: "subgroup"
---
**Code speak**: How to show mean/median by subgroup

**Context Example**: How to show average or median age of all mothers in every year (2000-2014)?

```stata
egen n_b11 = count(b11), by(year)
egen mean_b11 = mean(b11), by(year)
tabdisp year, c(n_b11 mean_b11)

```

###### Steps: Make two new variables and then display results:

1. Make a new variable that tells us the # of mothers who responded in each year.  
2. Make a new variable that tells us the mean ages of mothers in the data set for each year. 
3. Display these two variables by year. 





