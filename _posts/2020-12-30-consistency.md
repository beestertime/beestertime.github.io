---
layout: post
title: "6. Repetitive commands & the importance of consistency "
description: "consistency"
keywords: "loops, foreach, consistency"
---
**Code speak**: How to loop over variables, looping, foreach

# Consistency and avoiding errors is key in coding
In some jobs, it’s important to ensure consistency and minimizing the risk of errors. In coding, we'd like to do the same thing, especially when we are doing repetitive tasks.

_To do this in coding, we can use loops._

```stata
forvalues x=1/25
  gen bagel `x'=plain if spread==`x'

```

## Practical takeaways 
> Consider using loops for any tasks you have to repeat 2+ 

###### Sources: 
https://datacarpentry.org/stata-economics/06-loops/
