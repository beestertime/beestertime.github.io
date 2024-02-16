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
| ------------- |
| 2018-05-23    | 
| 2017-09-01    | 
| add this date | 
| 44287         |
| 22-09-01      |

##### This date column is a crunchy challenge because we notice a few things: 
1. We have numeric dates (this is good - yay!)
2. We have excel dates i.e. the five digit sequence
3. We have typos in our date values i.e. missing part of the year element


## WHAT DO WE DO????????


##### Finally, let's play our secret weapon: 
```python
df <- df %>%
  mutate(date_ex = convert_to_date(date_ex, character_fun = lubridate::dmy))
```
