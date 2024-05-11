# Algorithmic Trading with AMD Stock

## Background

You work at a well-established trading firm and have been tasked with demonstrating the capabilities of algorithmic trading to your Board of Directors. Your assignment is to develop a simple trading algorithm using R.

## Data Loading

Make sure to load the necessary libraries and prepare the dataset for analysis.

```r
# Load necessary libraries
library(dplyr)
library(ggplot2)

# Data for AMD stock
dates <- seq(as.Date("2019-09-30"), length.out = 10, by = "days")
amd_data <- c(28.99, 28.76, 28.31, 28.68, 29.01, 28.93, 28.23, 28.46, 28.38, 29.75)
amd_df <- data.frame(Date = dates, Close = amd_data)
