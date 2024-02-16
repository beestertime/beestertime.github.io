---
layout: post
title: "1. R: The case of messy data"
comments: true
description: " The case of messy data"
keywords: "date data"
---

##### Today let's talk about R and messy date data. 

##### Imagine you imported an excel data file into R and have a column like this:

| date_ex       | 
| -------------:|
| 2018-05-23    | 
| 2017-09-01    | 
| add this date | 
| 44287         |
| 22-09-01      |

##### This date column is a crunchy challenge because we notice a few things: 
1. We have numeric dates (this is good - yay!)
2. We have excel dates i.e. the five digit sequence
3. We have typos in our date values i.e. missing part of the year element

Having dates in different formats make it difficult to do further analyses. 

## How can we clean this column so that in the end, all values are listed in a standard, consistent date format? 
___
___

##### **There are different ways of solving this challenge, including using regex or regular expressions. Below, I'll show an approach that does not necessitate knowing those concepts. ** 

## 1. Remove non-dates from date column
##### First, let's remove the non-date from our date column and assume an ideal, simplified scenario that there are no repercussions to our analysis by doing so. We subset the data using the `filter` function and indicate we want to exclude the string of interest using `!` and `grepl`.

```python
df <- df %>% 
  filter(!grepl("add this date", date_ex))
```

## 2. Fix the date typo
##### We'll correct the date typo by creating a new variable `mutate` with the same name as our original date variable and convert any string matching the typo sequence to the new, corrected string using `case_when`. Otherwise, keep the values the same.
```python
df <- df %>% 
  mutate(date_ex = case_when (
    date_start == "22-09-01 " ~ "2022-09-01 ",
    TRUE ~ date_ex
  ))
```

## 3. Convert mixed excel and numeric dates to one date format
#####
```python
df <- df %>%
  mutate(date_ex = convert_to_date(date_ex, character_fun = lubridate::dmy))
```
