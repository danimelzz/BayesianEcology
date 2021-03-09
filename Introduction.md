# Introduction

## Bayes' rule

Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was comnonlly used to test whether a patient had HIV or not. However, ELISA is not 100% accurate, because some tests result in false positives (ELISA+ ∣ HIV-) and false negatives (ELISA- ∣ HIV+). This was really problematic until the invention of Western Blot tests, in which the chances of error are lower. 

**Example 1.** Consider the following probabilities:
- True positive rate, also called sensitivity: P(ELISA+ ∣ HIV+) = 0.93
- True negative rate, also called specifity: P(ELISA- ∣ HIV-) = 0.99
- Prevalence of HIV in USA: P(HIV+) = 0.00148

What's the probability that a person actually have HIV given a positive HIV detection by ELISA (i.e., P(HIV+ ∣ ELISA+))?

**R:** First, we need to remember the conditional probability formula:
![Fig1](https://www.google.com/url?sa=i&url=https%3A%2F%2Fdzone.com%2Farticles%2Fconditional-probability-and-bayes-theorem&psig=AOvVaw0pTgieuM9s2TbcfNJUWbCM&ust=1615350815184000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLDb3fCwou8CFQAAAAAdAAAAABAP)

Now, we can calculate it:
P(HIV+ ∣ ELISA+) = P(HIV+ & ELISA+) / P(ELISA+)
P


Bayes' Rule
![Fig2](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)
 



| 5 | 3 | 3 | 2 |
|---|---|---|---|
| 2 | 4 | 1 | 1 |




```
```
