
```r
# EXEMPLARY CODE CHUNK

library(tidyverse)
library(knitr)


summary_table <- function(data, group_var, value_var) {
  
  data_clean <- data %>%
    filter(
      !is.na({{ group_var }}),
      !is.na({{ value_var }})
    )
  
  summary_stats <- data_clean %>%
    group_by({{ group_var }}) %>%
    summarise(
      obs = n(),
      mean = mean({{ value_var }}, na.rm = TRUE),
      sd = sd({{ value_var }}, na.rm = TRUE),
      median = median({{ value_var }}, na.rm = TRUE),
      percent = n() / nrow(data_clean) * 100
    ) %>%
    ungroup()
  
  total_row <- data_clean %>%
    summarise(
      obs = n(),
      mean = mean({{ value_var }}, na.rm = TRUE),
      sd = sd({{ value_var }}, na.rm = TRUE),
      median = median({{ value_var }}, na.rm = TRUE),
      percent = 100
    ) 
  
  final_table <- bind_rows(summary_stats, total_row)
  
  final_table[[1]][is.na(final_table[[1]])] <- "Total"
  
  knitr::kable(final_table, digits = 1, caption = "Summary Statistics Table")
}
```
```r
# OUTPUT

summary_table(mtcars, cyl, mpg)

Table: Summary Statistics Table

|cyl   | obs| mean|  sd| median| percent|
|:-----|---:|----:|---:|------:|-------:|
|4     |  11| 26.7| 4.5|   26.0|    34.4|
|6     |   7| 19.7| 1.5|   19.7|    21.9|
|8     |  14| 15.1| 2.6|   15.2|    43.8|
|Total |  32| 20.1| 6.0|   19.2|   100.0|


summary_table(mtcars, am, hp)

Table: Summary Statistics Table

|am    | obs|  mean|   sd| median| percent|
|:-----|---:|-----:|----:|------:|-------:|
|0     |  19| 160.3| 53.9|    175|    59.4|
|1     |  13| 126.8| 84.1|    109|    40.6|
|Total |  32| 146.7| 68.6|    123|   100.0|
```
