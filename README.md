# Case-Study-Gas-Price-Comparison
This project serves as a case study to practice data analysis with Excel, data visualization with Tableau, and creation of .rmd file.

Data interpretation:

From the visualizations above, we can interpret data for the differentiation in gas prices between the regions and including California.

1. We can see an overall trend of gas prices increasing over the years with California and the West coast being above the average U.S. prices. The overall trend of gas prices move similarly compare to each other as they both go up and down at same intervals. There is no out of the ordinary fluctuations from any regions but it seems that gas prices had a massive increase in price from 2020 to 2022. 
2. East Coast shows to be mostly at the national average while Midwest is slightly under the average. West Coast is above the national average and has been increasingly so over the years. West Coast gas prices is much higher than the other regions in comparison to the national average. Below shows a bit more information to show comparison on the percentage difference

```{r setup2, include=TRUE}
# Load scales package for formatting
library(scales)

# Create list of years and values for calculation
data <- data.frame(
  years = c(2000, 2005, 2010, 2015, 2020, 2023), 
  national = c(1.48, 2.27, 2.78, 2.43, 2.17, 3.54),
  west = c(1.63, 2.43, 3.03, 2.98, 2.82, 4.54)
)

# Calculate percentage difference
data$percentage_difference <- abs(((data$west - data$national) / data$national) * 100)

# Format percentage values
data$percentage_difference <- percent(data$percentage_difference, scale = 1)

# Format columns containing currency values
data$west <- dollar_format()(data$west)
data$national <- dollar_format()(data$national)

# Print the formatted data frame
knitr::kable(data)

```
