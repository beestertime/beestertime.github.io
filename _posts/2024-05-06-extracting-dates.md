---
layout: post
title: "2. R: Extracting dates from strings"
comments: false
description: "Extracting dates from strings"
keywords: "extract dates from strings"
---

## THE DATA: 
Instead of dates, you have dates embedded in string or characters:

###### Table 1
| date_ex       |               |
| ------------- | ------------- |
| vr_2018-05-23 |               |
| fi_2017-09-01 |               |
| pu_2022-01-01 |               |
| im_2014-11-13 |               |

___

## THE GOAL: 
Extract only dates from the string into a new column. In other words, make a new date variable using the date extraced from the text.

___

## THE APPROACH: 

To solve this problem, we can use three types of commands or concepts: 
1) `mutate` : creates a new column
2) `str_extract` : extracts strings that match a specified string
3) `regex` : otherwise known as regular expressions or text shortcuts that describe patterns in a string

Assembled, it'll look like this:

```python
df <- df %>% 
  mutate(date = str_extract(titles, '(\\d{1,4}-\\d{1,2}-\\d{1,2}'))
```

>How do we know what pattern we'd like R to extract?

If we refer to Table 1, we see that the dates embedded in each string is in the form yyyy-mm-dd. Based on this observation, we'll instruct R using the line `(\\d{1,4}-\\d{1,2}-\\d{1,2}')` to extract any values listed in the "title" column that:
* matches any number with 1 to 4 digits
* matches a hyphen
* matches any number with 1 to 2 digits
* matches a hypen
* matches any number with 1 to 2 digits

___

## THE RESULT: 

###### Table 2
| date_ex       |    date        |
| ------------- | -------------- |
| vr_2018-05-23 |  2018-05-23    |
| fi_2017-09-01 |  2017-09-01    |
| pu_2022-01-01 |  2022-01-01    |
| im_2014-11-13 |  2014-11-13    |

