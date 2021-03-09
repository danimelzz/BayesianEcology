# Introduction

## Bayesian vs Frequentist
The principal differences between **frequentist and Bayesian** approaches lies on the probability definition. In frequentist context, probability is the proportion of times that an event occurs in an infinite number of times. In Bayesian context, probability is the belief degree, in which we generate posterior probabilities based on prior information (belief). Thus, it's rationable that different probability definitions result in different methods of inference: 

-Frequentist inference: describes the confidence level as the proportion of random samples from the same population that produced confidence intervals which contain the true population parameter; 

- Bayesian inference

## Bayes' Theorem and Updating

Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was commonly used to test whether a patient had HIV or not. However, ELISA is not 100% accurate, because some tests result in false positives (ELISA+ ∣ HIV-) and false negatives (ELISA- ∣ HIV+). This was really problematic until the invention of Western Blot tests, in which the chances of error are lower. 

### Example 1. Bayes' Theorem 
Consider the Bayes' Theorem: 

![Fig2](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)

And the following probabilities:
- True positive rate, also called sensitivity: P(ELISA+ ∣ HIV+) = 0.93
- True negative rate, also called specifity: P(ELISA- ∣ HIV-) = 0.99
- Prevalence of HIV in USA: P(HIV+) = 0.00148

What's the probability that a person actually have HIV given a positive HIV detection by ELISA? In other words, what's P(HIV+ ∣ ELISA+)?

```
Using Bayes' Theroem:
P(HIV+ ∣ ELISA+) = (P(ELISA+ ∣ HIV+) * P(HIV+)) / P(ELISA+)

First, let's calculate the numerator:
P(ELISA + ∣ HIV+) * P(HIV+) = 0.93 * 0.00148 = 0.0013764

Second, let's calculate the denominator: 
P(ELISA+) = P(ELISA + ∣ HIV+)* P(HIV+) + P(ELISA + ∣ HIV-) * P(HIV-) = 0.0013764 + (1-0.99)(1-0.00148) = 0.0013764 + 0.0099852 = 0.0113616

Finally:
P(HIV+ ∣ ELISA+) = 0.0013764 / 0.0113616 = 0.12
```

### Example 2. Bayes Updating
In Example 1, we concluded that if you were positively diagnosed for HIV using ELISA test, there is only 12% of probability that you actually have HIV. However, you certainly want to have more certainty about it and thus you test your blood again. Assuming that there is an independence between the first and the second test, what is the probability of being HIV positive if also the second ELISA test comes back positive?

```
First, it's important to know that the posterior probability obtained in the previous iteration (Example 1) will be the prior information in the Bayes updating. In other words, now we will have P(HIV+) = 0.12. 

Using Bayes' Theorem:
P(HIV+ ∣ 2nd ELISA+) = (P(ELISA+ ∣ HIV+) * P(HIV+)) / P(ELISA+)

First, let's calculate the numerator:
P(ELISA+ ∣ HIV+) * P(HIV+) = 0.93 * 0.12 = 0.1116

Second, let's calculate the denominator:
P(ELISA+) =  P(ELISA + ∣ HIV+)* P(HIV+) + P(ELISA + ∣ HIV-) * P(HIV-) = 0.1116 + (1-0.99)(1-0.12) = 0.1116 + 0.0088 = 0.1204

Finally:
P(HIV+ ∣ 2nd ELISA+) = 0.1116 / 0.1204 = 0.93
```



|        |  HIV+ |  HIV- |
|--------|-------|-------|
| ELISA+ |   3   |   1   |
| ELISA- |   4   |   1   |



```
```
