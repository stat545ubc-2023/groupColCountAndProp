# groupColCountAndProp

The 'groupColCountAndProp' function streamlines data analysis by offering a straightforward method for grouping and summarizing datasets. Specifically, it takes a dataset, groups it by a column of your choice, and subsequently calculates the count and proportion of unique entries in another column, all within each group. This utility is particularly handy during the exploratory stages of data analysis, as it transforms the complex task of grouped summarization into a seamless operation. The function's intuitive design ensures that even users with minimal programming experience can efficiently derive meaningful insights from their data.

## Installation

You can install the development version of groupColCountAndProp from [GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("stat545ubc-2023/assignment-b2-lurkstalker")
```

## Example

This is a basic example which shows you how to solve a common problem:

``` r
library(groupColCountAndProp)
## basic example code
test_data <- data.frame(
  Species = c("Oak", "Maple", "Oak", "Pine", "Maple", "Pine", NA),
  Height = c(10, 15, 20, 25, 30, 35, 40)
)

# Vector with no NA's
result1 <- group_distinct_col_count_prop(test_data[1:6, ], "Species", "Height")
# # A tibble: 3 × 3
#   Species total proportion
#   <chr>   <int>      <dbl>
# 1 Maple       2      0.333
# 2 Oak         2      0.333
# 3 Pine        2      0.333

# Vector that has NA's
result2 <- group_distinct_col_count_prop(test_data, "Species", "Height")
# # A tibble: 4 × 3
#   Species total proportion
#   <chr>   <int>      <dbl>
# 1 Maple       2      0.286
# 2 Oak         2      0.286
# 3 Pine        2      0.286
# 4 NA          1      0.143
```
