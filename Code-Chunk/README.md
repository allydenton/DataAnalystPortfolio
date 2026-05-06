
```{r}
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

summary_table(mtcars, cyl, mpg)

summary_table(mtcars, am, hp)
```
