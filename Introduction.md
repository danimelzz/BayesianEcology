# Introduction

## Bayes' rule
Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was comnonlly used to test whether a pacient had HIV or not. However, ELISA is not 100% accurate: 

P(\text{ELISA is positive} \mid \text{Person tested has HIV}) = 93\% = 0.93.

| 5 | 3 | 3 | 2 |
|---|---|---|---|
| 2 | 4 | 1 | 1 |
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
