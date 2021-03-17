# Lesson 2: Bayesian Inference for continuous variables

This lesson aims to present a continuous version of Bayes' Rule with and without conjugacy. What is conjugacy? A brief overview:

- Conjugacy: occurs when the posterior distribution is in the same family of probability density functions (pdf) as the prior belief, but with new parameter values, which have been updated to reflect what we have learned from the data. 
- Non-conjugacy:  there is usually no simple mathematical expression, and one must resort to computation. 

Finally, we discuss the credible intervals in Bayesian Inference, which can be interpreted as analogous to confidence intervals in frequentist framework. 

## 2.1 Elicitation and Conjugacy

Discrete and continuous variables have different probability functions. See:

- Probability mass function (pmf): used for discrete variables (e.g., in binomial distributions); pmf tells us the probability that the random variable takes each of the possible values
- Probability density function (pdf): used for continuous variables (e.g., in normal distributions); because continuous variables have probability zero of taking any single value, we can only talk about the probability within some interval (i.e. the area between two values under a pdf curve)

https://miro.medium.com/max/1156/1*MGABHsIerbdfG70sEL4ysA.png

## 2.2 Conjugate families

The property that the posterior distribution follows the same parametric form as the prior distribution is called **conjugacy**. In other words, if the posterior distributions p(θ | x) are in the same probability distribution family as the prior probability distribution p(θ), the prior and posterior are then called conjugate distributions, and the prior is called a conjugate prior for the likelihood function p(x | θ).

## 2.3 Credible Intervals and Inference
