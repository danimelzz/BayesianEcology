# Introduction

## 1. Bayesian vs Frequentist
![Fig1](https://miro.medium.com/max/1932/0*eqNjjx0pcgm4_GPU.png)

The principal differences between **frequentist and Bayesian** approaches lies on the probability definition. In frequentist context, probability is the proportion of times that an event occurs in an infinite number of times. In Bayesian context, probability is the belief degree, in which we generate posterior probabilities based on prior information (belief). Thus it's rationable that different probability definitions result in different methods of inference: 

- Frequentist inference: describes the confidence level as the proportion of random samples from the same population that produces confidence intervals (CI) which contain the true population parameter. Thus a frequentist cannot say "I'm 95% confident that 60% to 70% of Brazilians think that neoliberalism will increase our social inequality", because the probability that a CI captures the population parameter is either 0 or 1. The correct interpretation is "95% of random samples capture the CI within which the population parameter - i.e., the proportion of Brazilians who think neoliberalism is socially terrible - is included".

- Bayesian inference: describes uncertainty as probability. Thus a Bayesian can say that there is a 95% chance that the credible interval contains the true parameter value.

## 2. Bayes' Theorem and Updating

Conditional probability is the starting point for understanding Bayesian thinking and is widely used in disease testing. During early 1980s, ELISA was commonly used to test whether a patient had HIV or not. However, ELISA is not 100% accurate, because some tests result in false positives (ELISA+ ∣ HIV-) and false negatives (ELISA- ∣ HIV+). This was really problematic until the invention of Western Blot tests, in which the chances of error are lower. 

### 2.1. Bayes' Theorem 
**Example 1.** Consider the Bayes' Theorem: 

![Fig2](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)

And the following probabilities:
- True positive rate, also called sensitivity: P(ELISA+ ∣ HIV+) = 0.93
- True negative rate, also called specifity: P(ELISA- ∣ HIV-) = 0.99
- Prevalence of HIV in USA: P(HIV+) = 0.00148

What's the probability that a person actually have HIV given a positive HIV detection by ELISA? In other words, what's P(HIV+ ∣ ELISA+)?

```
*note: this is not a R code, but the answer for example 1*

Using Bayes' Theroem:
P(HIV+ ∣ ELISA+) = (P(ELISA+ ∣ HIV+) * P(HIV+)) / P(ELISA+)

First, let's calculate the numerator:
P(ELISA + ∣ HIV+) * P(HIV+) = 0.93 * 0.00148 = 0.0013764

Second, let's calculate the denominator: 
P(ELISA+) = P(ELISA + ∣ HIV+)* P(HIV+) + P(ELISA + ∣ HIV-) * P(HIV-) = 0.0013764 + (1-0.99)(1-0.00148) = 0.0013764 + 0.0099852 = 0.0113616

Finally:
P(HIV+ ∣ ELISA+) = 0.0013764 / 0.0113616 = 0.12
```

### 2.2. Bayes Updating
**Example 2.** In Example 1, we concluded that if you were positively diagnosed for HIV using ELISA test, there is only 12% of probability that you actually have HIV. However, you certainly want to have more certainty about it and thus you test your blood again. Assuming that there is an independence between the first and the second test, what is the probability of being HIV positive if also the second ELISA test comes back positive?

```
*note: this is not a R code, but the answer for example 2*

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

## 3. Inference for proportions
### 3.1 Frequentist approach using R
<div style="text-align:center"><img src="https://oliveridleyproject.org/wp-content/uploads/2019/06/Green-turtle-with-fibropapillomatosis-tumors-Kenya.jpg" /></div>

**Example 3.** Consider a hypothetic context in which 40 sea turtles are used in a research about the efficacy of a new treatment against fibropapillomatosis (FP). Half of the animals (20 out of 40 turtles) is placed in a control group without any medicine and the other half is allocated in treatment group with medicine (20 out of 40). In the treatment group, 4 out of 20 turtles expressed FP. In the control group, 16 out of 20 turtles expressed FP. Is this treatment effective?

**R:** If no efficacy differences are found between the treatment and control groups (null hypothesis: H0), then the probability that a FP+ turtle comes from the treatment group (p) should be 0.5. If treatment is more effective than control (alternative hypothesis: H1), then the probability that a FP+ turtle comes from the treatment group (p) should be less than 0.5. Since H0 states that the probability of express FP is 0.5, we can calculate the p-value from 20 independent Bernoulli trials where the probability of turtles expressing FP is 0.5. The outcome of this experiment is 4 FP+ turtles out of 20, so the goal is to obtain 4 or fewer FP+ turtles in the 20 Bernoulli trials (n = 20; k = 4; p = 0.5).

```
#Calculate the probability 
sum(dbinom(0:4, size = 20, p = 0.5))
```

```
## [1] 0.005908966
```

We can conclude that the chance of turtles in the treatment group expressing FP is 0.005. Thus we reject the H0 and accept the H1. The treatment is effective against FP according to frequentist inference.

### 3.2 Bayesian approach using R

**Example 4.** Now, let's use the same data from **Example 3** (n = 20; k = 4; p = 0.5) to perform a Bayesian Inference. If there isn't any difference between the treatment and control groups, the probability that a FP+ turtle comes from treatment is 0.5 (p=0.5) for null hypothesis in a frequentist framework. In contrast, Bayesian framework assumes some prior parameters on the models: p can take on any value between 0 and 1. Let's simplify it assuming that p varies from 10%, 20%, 30%, up to 90%, in which p = 10% means that among 20 FP+ turtles, it is expected that 2 FP+ turtles come from treatment group. Suppose the prior probabilities for each of the nine models presented below: 


| MODEL                   |  0.10 |  0.20 |  0.30 |  0.40 |  0.50 |  0.60 |  0.70 |  0.80 |  0.90 |
|-------------------------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| PRIOR P(model)          |  0.06 |  0.06 |  0.06 |  0.06 |  0.52 |  0.06 |  0.06 |  0.06 |  0.06 |

This prior incorporates two beliefs: the probability of p=0.5 is highest, and the benefit of the treatment is symmetric. 

Do you remember the Bayes' Theorem? We need to calculate the numerator (likelihood and prior information) and denominator (P data).

![Fig2](https://wikimedia.org/api/rest_v1/media/math/render/svg/2634e395f47aaf16f5deb5b09a979afc646d83eb)

When we have multiple prior probabilities, we need to calculate the likelihood for each model in order to obtain the posterior probabilities. Given that the likelihood is P (data|model) = P (k=4 | n=20, p), let's calculate it in R:

```
## Calculating likelihood
p <- seq(from=0.1, to=0.9, by=0.1)
prior <- c(rep(0.06, 4), 0.52m rep(0.06, 4))
likelihood <- dbinom(4, size=20, prob=p)
likelihood
```

```
[1] 8.977883e-02 2.181994e-01 1.304210e-01 3.499079e-02 4.620552e-03 2.696862e-04 5.007558e-06
[8] 1.300570e-08 3.178804e-13
```

```
## Calculating posterior
numerator <- prior * likelihood
denominator <- sum (numerator)
posterior <- numerator / denominator
sum (posterior)
```

```
[1] 1
```

| MODEL                     |  0.10 |  0.20 |  0.30 |  0.40 |  0.50 |  0.60 |  0.70 |  0.80 |  0.90 |
|---------------------------|-------|-------|-------|-------|-------|-------|-------|-------|-------|
| PRIOR P(model)            |   0.06|   0.06|   0.06|   0.06|   0.52|   0.06|   0.06|   0.06|   0.06|
| LIKELIHOOD P(data I model)| 0.0898|	0.2182|	0.1304|	0.0350|	0.0046|	0.0003|  0.00 |	 0.00	|   0.00|
| P(data I model) x P(model)| 0.0054| 0.0131|	0.0078|	0.0021|	0.0024|	0.0000|	  0.00|  0.00	|   0.00|
| Posterior P(model I data) | 0.1748|	0.4248|	0.2539|	0.0681|	0.0780|	0.0005|	  0.00|	  0.00| 	0.00|

The model with p=0.2 has the highest posterior probability (=0.42). This is not surprising, because 4 out of 20 FP+ turtles from treatment group equals to 20%. Therefore, it's likely that there are differences between the efficacy of treatment and control groups. Note that posterior probability of p=0.5 dropped from 52% (prior belief) to 7.8% (posterior), which demonstrates how we update our beliefs.  
