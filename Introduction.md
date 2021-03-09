# Introduction

## Bayes' rule

Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was comnonlly used to test whether a patient had HIV or not. However, ELISA is not 100% accurate, because some tests result in false positives (ELISA+ ∣ HIV-) and false negatives (ELISA- ∣ HIV+). This was really problematic until the invention of Western Blot tests, in which the chances of error are lower. 

**Example 1.** Consider the following probabilities:
- True positive rate, also called sensitivity: P(ELISA+ ∣ HIV+) = 0.93
- True negative rate, also called specifity: P(ELISA- ∣ HIV-) = 0.99
- Prevalence of HIV in USA: P(HIV+) = 0.00148

And the Bayes' Theorem: 
![Fig2](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)

What's the probability that a person actually have HIV given a positive HIV detection by ELISA? In other words, what's P(HIV+ ∣ ELISA+)?

**R:** 
Using Bayes' Theroem:
- P(HIV+ ∣ ELISA+) = (P(ELISA+ ∣ HIV+) * P(HIV+)) / P(ELISA+)

First, let's calculate the numerator:
- P(ELISA + ∣ HIV+) * P(HIV+) = 0.93 * 0.00148 = 0.0013764

Second, let's calculate the denominator: 
- P(ELISA+) = P(ELISA + ∣ HIV+)* P(HIV+) + P(ELISA + ∣ HIV-) * P(HIV-) = 0,0013764 + (1-0.99)(1-0.00148) = 0,0013764 + 0,0099852 = 0.0113616

Finally:
- P(HIV+ ∣ ELISA+) = 0.0013764 / 0.0113616 = 0,12



| 5 | 3 | 3 | 2 |
|---|---|---|---|
| 2 | 4 | 1 | 1 |




```
```
