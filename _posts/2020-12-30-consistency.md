---
layout: post
title: "6. Repetitive commands & avoiding errors "
description: "consistency"
keywords: "loops, foreach, consistency"
---
**Code speak**: How to loop over variables

**Context Example**: How to be reduce errors in code? Is there a way to get code to automatically do repetitive tasks?

# Avoiding errors
In most jobs, we want to minimize the risk of errors. In coding, we'd like to do the same thing, especially when we are doing repetitive tasks.

_To do this in coding, we can use loops._

```stata
forvalues x=1/25 }
  gen bagel `x'=plain if marmalade==`x'
  }
```
## Break down 
* forvalues is a command commonly used in coding repetitive tasks
* 1/25 means we want to list 1-25 values in increments of 1 
* gen means we want to _generate_ or create a new variable called bagel, that will represent _plain_ (or contain the value plain) **IF** the marmalade variable is equal to ``x'`
* == means "equal to". It's a type of [syntax](https://www.stata.com/manuals13/psyntax.pdf)
* ``x'`` is a placeholder variable. _Note_ that this command uses a grave accent at the beginning and an apostrophe at the end. 
* {} are called curly brackets or braces. Stata requires one } on the same line as the forvalues command and another } on its own line to end the command. 

## Practical takeaways 
* Consider using [loops](https://datacarpentry.org/stata-economics/06-loops/) for any tasks you have to repeat 2+ 
* Looping helps you achieve consistency and reduce risk of coding errors (not necessarily to save on typing)

###### Sources: 
Nice website that clearly explains looping with examples and exercises: https://datacarpentry.org/stata-economics/06-loops/
https://data.library.virginia.edu/stata-basics-foreach-and-forvalues/
