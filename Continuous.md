# Lesson 2: Bayesian Inference for continuous variables

This lesson aims to present a continuous version of Bayes' Rule with and without conjugacy. Finally, we discuss the credible intervals in Bayesian Inference, which can be interpreted as analogous to confidence intervals in frequentist framework. 

## 2.1 Probability Functions, Elicitation, and Conjugacy

Before explain the Bayesian Inference for continuous variables, three concepts must be clarified: (i) probability functions, (ii) elicitation, and (iii) conjugacy. 

(i) Discrete and continuous variables have different **probability functions**. See:

- Probability mass function (pmf): used for discrete variables (e.g., in binomial distributions); pmf tells us the probability that the random variable takes each of the possible values
- Probability density function (pdf): used for continuous variables (e.g., in normal distributions); because continuous variables have probability zero of taking any single value, we can only talk about the probability within some interval (i.e. the area between two values under a pdf curve)

![Fig1](https://abaqus-docs.mit.edu/2017/English/SIMA3DXRefImages/pdf-defin-nls.png)

(ii) **Prior elicitation** is the process by which we attempt to construct the most suitable prior distribution for θ. Sometimes, you may know nothing at all and hence you are incapable to inform prior distribution for your model. In these cases, a flexible family distribution is **Beta family**, in which p ~ beta (α, β):

- p ~ beta (1,1) equals to uniform distribution
- p ~ beta (1,5) is right skewed
- p ~ beta (5,1) is left skewed

![Fig2](https://miro.medium.com/max/882/1*n1q2lm3-2Npx2AMCWUaYMQ.png)

(iii) What is **conjugacy**? A brief overview:

- Non-conjugacy:  there is usually no simple mathematical expression, and one must resort to computation. 
- Conjugacy: occurs when the posterior distribution is in the same family of probability density functions (pdf) as the prior belief, but with new parameter values, which have been updated to reflect what we have learned from the data. 

Finally, let's remember the Bayes' rule used for discrete variables:

![Fig3](https://camo.githubusercontent.com/1245d0488d557c84c524d03b414e6db823aa173eb1c191d0af4d7d7824c76f0e/68747470733a2f2f77696b696d656469612e6f72672f6170692f726573745f76312f6d656469612f6d6174682f72656e6465722f7376672f32363334653339356634376161663136663564656235623039613937396166633634366438336562)

Bayes' rule doesn't apply to continuous variables, because the denominator sums over all possible values. Thus, it's less intuitive calculating all values from an interval with infinite values for continuous variables. To complete this task, one must perform integration:

![Fig4](https://www.statisticalengineering.com/images/Bayes_Theorem.gif)

## 2.2 Conjugate families
There is an infinite number of pmfs and pdfs, but some distributions are so important that they receive their own name: 

- Continuous: normal, uniform, beta, gamma
- Discrete: binomial, Poisson


The property that the posterior distribution follows the same parametric form as the prior distribution is called **conjugacy**. In other words, if the posterior distributions p(θ | x) are in the same probability distribution family as the prior probability distribution p(θ), the prior and posterior are then called conjugate distributions, and the prior is called a conjugate prior for the likelihood function p(x | θ).

## 2.3 Credible Intervals and Inference
