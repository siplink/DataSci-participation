---
title: "s06 Exercises: Pivoting and tidy data"
output: 
  html_document:
    keep_md: true
    theme: paper
---


```r
library(tidyverse)
lotr  <- read_csv("https://raw.githubusercontent.com/jennybc/lotr-tidy/master/data/lotr_tidy.csv")
guest <- read_csv("https://raw.githubusercontent.com/USF-Psych-DataSci/Classroom/master/data/wedding/attend.csv")
email <- read_csv("https://raw.githubusercontent.com/USF-Psych-DataSci/Classroom/master/data/wedding/emails.csv")
```

<!---The following chunk allows errors when knitting--->




## Exercise 1: Univariate Pivoting

Consider the Lord of the Rings data:


```r
lotr
```

```
## # A tibble: 18 x 4
##    Film                       Race   Gender Words
##    <chr>                      <chr>  <chr>  <dbl>
##  1 The Fellowship Of The Ring Elf    Female  1229
##  2 The Fellowship Of The Ring Hobbit Female    14
##  3 The Fellowship Of The Ring Man    Female     0
##  4 The Two Towers             Elf    Female   331
##  5 The Two Towers             Hobbit Female     0
##  6 The Two Towers             Man    Female   401
##  7 The Return Of The King     Elf    Female   183
##  8 The Return Of The King     Hobbit Female     2
##  9 The Return Of The King     Man    Female   268
## 10 The Fellowship Of The Ring Elf    Male     971
## 11 The Fellowship Of The Ring Hobbit Male    3644
## 12 The Fellowship Of The Ring Man    Male    1995
## 13 The Two Towers             Elf    Male     513
## 14 The Two Towers             Hobbit Male    2463
## 15 The Two Towers             Man    Male    3589
## 16 The Return Of The King     Elf    Male     510
## 17 The Return Of The King     Hobbit Male    2673
## 18 The Return Of The King     Man    Male    2459
```

1. Would you say this data is in tidy format?

   <!-- Describe why or why not in this space. -->

2. Widen the data so that we see the words spoken by each race, by putting race as its own column.


```r
(lotr_wide <- lotr %>% 
  pivot_wider(FILL_THIS_IN = c(-Race, -Words), 
              FILL_THIS_IN = Race, 
              FILL_THIS_IN = Words))
```

```
## Error in pivot_wider(., FILL_THIS_IN = c(-Race, -Words), FILL_THIS_IN = Race, : unused arguments (FILL_THIS_IN = c(-Race, -Words), FILL_THIS_IN = Race, FILL_THIS_IN = Words)
```

3. Re-lengthen the wide LOTR data from Question 2 above.


```r
lotr_wide %>% 
  pivot_longer(FILL_THIS_IN = FILL_THIS_IN, 
               names_to  = FILL_THIS_IN, 
               values_to = FILL_THIS_IN)
```

```
## Error in eval(lhs, parent, parent): object 'lotr_wide' not found
```


## Exercise 2: Multivariate Pivoting

Congratulations, you're getting married! In addition to the wedding, you've 
decided to hold two other events: a day-of brunch and a day-before round of 
golf. You've made a guestlist of attendance so far, along with food preference 
for the food events (wedding and brunch).


```r
guest %>% 
  DT::datatable(rownames = FALSE)
```

<!--html_preserve--><div id="htmlwidget-0d52aac51d4b6bab6c3d" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-0d52aac51d4b6bab6c3d">{"x":{"filter":"none","data":[[1,1,1,1,2,2,3,4,5,5,5,6,6,7,7,8,9,10,11,12,12,12,12,12,13,13,14,14,15,15],["Sommer Medrano","Phillip Medrano","Blanka Medrano","Emaan Medrano","Blair Park","Nigel Webb","Sinead English","Ayra Marks","Atlanta Connolly","Denzel Connolly","Chanelle Shah","Jolene Welsh","Hayley Booker","Amayah Sanford","Erika Foley","Ciaron Acosta","Diana Stuart","Cosmo Dunkley","Cai Mcdaniel","Daisy-May Caldwell","Martin Caldwell","Violet Caldwell","Nazifa Caldwell","Eric Caldwell","Rosanna Bird","Kurtis Frost","Huma Stokes","Samuel Rutledge","Eddison Collier","Stewart Nicholls"],["PENDING","vegetarian","chicken","PENDING","chicken",null,"PENDING","vegetarian","PENDING","fish","chicken",null,"vegetarian",null,"PENDING","PENDING","vegetarian","PENDING","fish","chicken","PENDING","PENDING","chicken","chicken","vegetarian","PENDING",null,"chicken","PENDING","chicken"],["PENDING","Menu C","Menu A","PENDING","Menu C",null,"PENDING","Menu B","PENDING","Menu B","Menu C",null,"Menu C","PENDING","PENDING","Menu A","Menu C","PENDING","Menu C","Menu B","PENDING","PENDING","PENDING","Menu B","Menu C","PENDING",null,"Menu C","PENDING","Menu B"],["PENDING","CONFIRMED","CONFIRMED","PENDING","CONFIRMED","CANCELLED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","CANCELLED","CONFIRMED","CANCELLED","PENDING","PENDING","CONFIRMED","PENDING","CONFIRMED","CONFIRMED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","PENDING","CANCELLED","CONFIRMED","PENDING","CONFIRMED"],["PENDING","CONFIRMED","CONFIRMED","PENDING","CONFIRMED","CANCELLED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","CANCELLED","CONFIRMED","PENDING","PENDING","PENDING","CONFIRMED","PENDING","CONFIRMED","CONFIRMED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","PENDING","CANCELLED","CONFIRMED","PENDING","CONFIRMED"],["PENDING","CONFIRMED","CONFIRMED","PENDING","CONFIRMED","CANCELLED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","CANCELLED","CONFIRMED","PENDING","PENDING","PENDING","CONFIRMED","PENDING","CONFIRMED","CONFIRMED","PENDING","PENDING","PENDING","CONFIRMED","CONFIRMED","PENDING","CANCELLED","CONFIRMED","PENDING","CONFIRMED"]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th>party<\/th>\n      <th>name<\/th>\n      <th>meal_wedding<\/th>\n      <th>meal_brunch<\/th>\n      <th>attendance_wedding<\/th>\n      <th>attendance_brunch<\/th>\n      <th>attendance_golf<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"columnDefs":[{"className":"dt-right","targets":0}],"order":[],"autoWidth":false,"orderClasses":false}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

1. Put "meal" and "attendance" as their own columns, with the events living in a new column.


```r
(guest_long <- guest %>% 
  pivot_longer(cols      = FILL_THIS_IN, 
               names_to  = FILL_THIS_IN,
               FILL_THIS_IN))
```

```
## Error: Can't subset columns that don't exist.
## [31mx[39m The column `FILL_THIS_IN` doesn't exist.
```

2. Use `tidyr::separate()` to split the name into two columns: "first" and 
"last". Then, re-unite them with `tidyr::unite()`.


```r
guest_long %>% 
  separate(FILL_THIS_IN, into = FILL_THIS_IN)
```

```
## Error in eval(lhs, parent, parent): object 'guest_long' not found
```

```r
  # unite(col = "name", FILL_THIS_IN, sep = FILL_THIS_IN)
```

3. Which parties still have a "PENDING" status for all members and all events?


```r
FILL_THIS_IN %>% 
  group_by(party) %>% 
  summarize(all_pending = all(attendance == "PENDING"))
```

```
## Error in eval(lhs, parent, parent): object 'FILL_THIS_IN' not found
```

4. Which parties still have a "PENDING" status for all members for the wedding?


```r
FILL_THIS_IN %>% 
  group_by(party) %>% 
  summarize(pending_wedding = all(FILL_THIS_IN == "PENDING"))
```

```
## Error in eval(lhs, parent, parent): object 'FILL_THIS_IN' not found
```


5. Put the data back to the way it was.


```r
guest_long %>% 
  pivot_wider(id_cols     = FILL_THIS_IN, 
              names_from  = FILL_THIS_IN, 
              names_sep   = "_", 
              values_from = FILL_THIS_IN)
```

```
## Error in eval(lhs, parent, parent): object 'guest_long' not found
```

6. You also have a list of emails for each party, in this worksheet under the 
   object `email`. Change this so that each person gets their own row. 
   Use `tidyr::separate_rows()`


```r
email %>% 
  separate_rows(FILL_THIS_IN, sep = FILL_THIS_IN)
```

```
## Error: Can't subset columns that don't exist.
## [31mx[39m The column `FILL_THIS_IN` doesn't exist.
```


## Exercise 3: Making tibbles

1. Create a tibble that has the following columns:

- A `label` column with `"Sample A"` in its entries.
- 100 random observations drawn from the N(0,1) distribution in the column `x`
  - "N" means the normal distribution. "(0, 1)" means mean = 0, sd = 1.
  - Use `rnorm()`
- `y` calculated as the `x` values + N(0,1) error. 


```r
n <- 100
FILL_THIS_IN(label = FILL_THIS_IN,
             FILL_THIS_IN = rnorm(n),
             FILL_THIS_IN)
```

```
## Error in FILL_THIS_IN(label = FILL_THIS_IN, FILL_THIS_IN = rnorm(n), FILL_THIS_IN): could not find function "FILL_THIS_IN"
```


2. Generate a Normal sample of size 100 for each combination of the following 
means (`mu`) and standard deviations (`sd`).


```r
n <- 100
mu <- c(-5, 0, 5)
sd <- c(1, 3, 10)
FILL_THIS_IN(mu = mu, sd = sd) %>% 
  group_by_all() %>% 
  mutate(z = list(rnorm(n, mu, sd))) %>% 
  FILL_THIS_IN
```

```
## Error in FILL_THIS_IN(mu = mu, sd = sd): could not find function "FILL_THIS_IN"
```


3. Fix the `experiment` tibble below (originally defined in the documentation 
of the `tidyr::expand()` function) so that all three repeats are displayed for 
each person, and the measurements are kept. Some code is given, but it doesn't
quite work. It needs a few adjustments. What are they?


```r
experiment <- tibble(
  name = rep(c("Alex", "Robert", "Sam"), c(3, 2, 1)),
  trt  = rep(c("a", "b", "a"), c(3, 2, 1)),
  rep = c(1, 2, 3, 1, 2, 1),
  measurement_1 = runif(6),
  measurement_2 = runif(6)
)
experiment %>% expand(name, trt, rep)
```

```
## # A tibble: 18 x 3
##    name   trt     rep
##    <chr>  <chr> <dbl>
##  1 Alex   a         1
##  2 Alex   a         2
##  3 Alex   a         3
##  4 Alex   b         1
##  5 Alex   b         2
##  6 Alex   b         3
##  7 Robert a         1
##  8 Robert a         2
##  9 Robert a         3
## 10 Robert b         1
## 11 Robert b         2
## 12 Robert b         3
## 13 Sam    a         1
## 14 Sam    a         2
## 15 Sam    a         3
## 16 Sam    b         1
## 17 Sam    b         2
## 18 Sam    b         3
```


