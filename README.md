# Introduction to Bayesian Statistics in Ecology
In this course, I will present an introduction to *Bayesian Statistics approach used in Ecology*.

---
'Bayesian inference is an important statistical tool that is increasingly being used by ecologists. In a Bayesian analysis, information available before a study is conducted is summarized in a quantitative model or hypothesis: the prior probability distribution. Bayes’ Theorem uses the prior probability distribution and the likelihood of the data to generate a posterior probability distribution. Posterior probability distributions are an epistemological alternative to P‐values and provide a direct measure of the degree of belief that can be placed on models, hypotheses, or parameter estimates. Moreover, Bayesian information‐theoretic methods provide robust measures of the probability of alternative models, and multiple models can be averaged into a single model that reflects uncertainty in model construction and selection. These methods are demonstrated through a simple worked example. Ecologists are using Bayesian inference in studies that range from predicting single‐species population dynamics to understanding ecosystem processes. Not all ecologists, however, appreciate the philosophical underpinnings of Bayesian inference. In particular, Bayesians and frequentists differ in their definition of probability and in their treatment of model parameters as random variables or estimates of true values. These assumptions must be addressed explicitly before deciding whether or not to use Bayesian methods to analyse ecological data.'
---  Ellison (2004)

![Fig1](https://github.com/danimelzz/BayesianEcology/blob/main/figures/Thomas-Bayes.jpg?raw=true)

## Materials
Here, you'll need to install R and, if you want, R Studio to facilitate our analyses. The following R packages will be loaded to perform the tutorials.

```
#Load the following R packages

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

## About the instructor
- [Daniel Y. M. Nakamura](http://www.instagram.com/danimelzz) 

## Lessons
- Introduction: Frequentist vs Bayesian, Bayes' Rule, and Inference for proportions

- Bayesian Inference: Continuous Variables and Credible Intervals

- Decision Making: Losses, Normal Data, and Comparing Normal Means

- Bayesian Regression: Simple vs Multiple Regressions, Uncertainty, and MCMC

## References
Ellison, A. M. (2004). Bayesian inference in ecology. Ecology letters, 7(6), 509-520.
