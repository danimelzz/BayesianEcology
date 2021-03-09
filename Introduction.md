# Introduction

## Bayes' rule

Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was comnonlly used to test whether a patient had HIV or not. However, ELISA is not 100% accurate, because some tests result in false positives (ELISA+ ∣ HIV-) and false negatives (ELISA- ∣ HIV+). This was really problematic until the invention of Western Blot tests, in which the chances of error are lower. 

**Example 1.** Consider the following probabilities:
- True positive rate, also called sensitivity: P(ELISA+ ∣ HIV+) = 0.93
- True negative rate, also called specifity: P(ELISA- ∣ HIV-) = 0.99
- Prevalence of HIV in USA: P(HIV+) = 0.00148

What's the probability that a person actually have HIV given a positive HIV detection by ELISA (i.e., P(HIV+ ∣ ELISA+))?

First, remember the Bayes' Rule
![Fig1](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)




| 5 | 3 | 3 | 2 |
|---|---|---|---|
| 2 | 4 | 1 | 1 |



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
