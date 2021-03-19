# Lesson 2: Bayesian Inference for continuous variables

This lesson aims to present a continuous version of Bayes' Rule with and without conjugacy. Finally, we discuss the credible intervals in Bayesian Inference, which can be interpreted as analogous to confidence intervals in frequentist framework. 

## 2.1 Probability Functions, Elicitation, and Conjugacy

Before explain the Bayesian Inference for continuous variables, three concepts must be clarified: (i) probability functions, (ii) elicitation, and (iii) conjugacy. 

Discrete and continuous variables have different **probability functions**. See:

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
- Conjugacy: occurs when the posterior distribution is in the same family of probability density functions (pdf) as the prior belief, but with new parameter values, which have been updated to reflect what we have learned from the data. For example, if your Binomial distribution is Bin(n,p), your prior belief about p is beta (x, y), and the number of success is 10 out of 50, hence your posterior distribution will be p|x ~ beta (x+10, y+50-10)

Finally, let's remember the Bayes' rule used for discrete variables:

![Fig3](https://camo.githubusercontent.com/1245d0488d557c84c524d03b414e6db823aa173eb1c191d0af4d7d7824c76f0e/68747470733a2f2f77696b696d656469612e6f72672f6170692f726573745f76312f6d656469612f6d6174682f72656e6465722f7376672f32363334653339356634376161663136663564656235623039613937396166633634366438336562)

Classical Bayes' rule doesn't apply to continuous variables, because the denominator P (B) sums over all possible values. Thus, it's less intuitive calculating all values from an interval with infinite values for continuous variables. To complete this task, one must perform **integrals**. Some authors point the limited computational power to calculate integrals as the main reason for the lack of popularity of Bayesian Inference throughout the 20th century.

## 2.2 Conjugate families
There is an infinite number of pmfs and pdfs, but some distributions are so important that they receive their own name: 

- Continuous: normal, uniform, beta, gamma
- Discrete: binomial, Poisson

**Example 1** Let's talk about Beta-Binomial distribution. Suppose that a new serum against the venom of *Bothrops jararaca* is being tested. 800 mice which receveid the jararaca venom were separated in two groups: 400 mice were treated with the old serum (group A) and 400 mice were treated with the new serum (group B). Among the 

![Fig4](https://biologo.com.br/bio/wp-content/uploads/2018/05/jararaca.jpg)

## 2.3 Credible Intervals and Inference
