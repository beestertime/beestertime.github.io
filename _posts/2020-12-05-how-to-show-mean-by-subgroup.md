---
layout: post
title: "3. How to show mean/median by subgroup"
comments: true
description: "How to show mean/median by subgroup"
keywords: "subgroup"
---

Example: How to show average or median age of all mothers in every year (2000-2014)?

```stata
egen n_b11 = count(b11), by(year)
egen mean_b11 = mean(b11), by(year)
tabdisp year, c(n_b11 mean_b11)

```

We’re going to make two new variables and then display results:

1) we’re going to make a new variable that tells us the # of mothers who responded in each year.  

2) we’re going to make a new variable that tells us the average or mean of the ages of the mothers in the data set for each year. 
3) we’re going to display these two variables by year. 





