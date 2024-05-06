---
layout: post
title: "2. R: Extracting dates from strings"
comments: false
description: "Extracting dates from strings"
keywords: "extract dates from strings"
---

## THE DATA: 
Instead of dates, you have dates embedded in string or characters:

| date_ex                            |             |
| ---------------------------------- |-------------|
| version_two_2018-05-23             |             |
| final report for review_2017-09-01 |             |
| publish this_2022-01-01            |             |
| draft for meeing_2014-11-13        |             |

## THE GOAL: 
Extract only dates from the string into a new column. In other words, make a new date variable using the date extraced from the text.

___
___

## THE APPROACH: 

To solve this problem, let's use three types of commands or concepts: 
1) mutate >> creates a new column
2) str_extract >> extracts strings that match a specified string
3) regex >> regular expressions or text shortcuts that describe patterns in a string

Assembled, it'll look like this:

```python
df <- df %>% 
  mutate(date = str_extract(titles, '(\\d{1,4}-\\d{1,2}-\\d{1,2}'))
```
