# Introduction

## Bayes' rule
```{r 2015gallupDating, echo = FALSE}
temp <- matrix(c(60, 86, 58, 21, 225, 255, 426, 450, 382, 1513, 315, 512, 508, 403, 1738), nrow = 3, byrow = TRUE)
rownames(temp) <- c('Used online dating site', 'Did not use online dating site', 'Total')
colnames(temp) <- c('18-29', '30-49', '50-64', '65+', 'Total')
knitr::kable(
  x = temp,
  booktabs = TRUE,
  caption = 'Results from a 2015 Gallup poll on the use of online dating sites by age group'
)
```

## 

```
# Load the following R packages
library(statsr)
library(BAS)
library(ggplot2)
library(dplyr)
library(BayesFactor)
library(knitr)
library(rjags)
library(coda) 
library(latex2exp)
library(foreign)
library(BHH2)
library(scales)
library(logspline)
library(cowplot)
library(ggthemes)
```
