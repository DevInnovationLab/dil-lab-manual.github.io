---
layout: default
title: Introduction to statistical power
grand_parent: Coding guides
parent: Power calculations
nav_order: 3
---


> Statistical power is defined as the probability, before a study is performed, that a particular comparison will achieve "statistical significance" at some predetermined level (typically a p-value below 0.05), given some assumed true effect size.
> A power analysis is performed by first hypothesizing an effect size, then making some assumptions about the variation in the data and the sample size of the study to be conducted, and finally using probability calculations to determine the chance of the p-value being below the threshold.

[Gelman, Hill, Vehktari (2020) Regression and Other Stories, Chapter 16]

First, it has to be clarified that null hypothesis significance testing (NHST) - and thus also statistical power - is a frequentist concept only[^1].
The question we want to answer is: **how large a sample do we have to collect in order to be reasonably sure of meeting the study objectives**?
Power calculations are not just useful for randomized evaluations, however, but also worth doing before we carry out studies on *purely observational data*.
Think of a scenario where an intervention or event has already happened, and we need to figure out whether it is worth the time and expense of collecting or trying to get access to data.
Power calculations are sometimes even worth doing on published/finished research.


<!-- As a next step in this chain of thought it is useful to have a personal heuristic in place to approximate a counterfactual benchmark, e.g. what sample size would the authors have needed, had the effect size been only half of the reported one. -->

## A useful Heuristic: "Sixteen S-squared over D-squared"

A rough approximation introduced by Lehr says that for a two sample t-test with power 80% and significance level 5%, the required sample size can be approximated by $$n \approx 16 \frac{\sigma^2}{\delta^2}$$, where $$\sigma$$ is the standard error of the variable of interest and $$\delta$$ the difference in means that we want to detect.


[^1]: A Bayesian would think about power differently. In essence, instead of focusing on frequencies of rejecting a null hypothesis when an alternative is true, a Bayesian would consider the posterior distribution of a parameter given the data. The strength of evidence for or against particular parameter values is expressed in terms of probability distributions. To analogously assess "power," a Bayesian might consider the probability that a future observation or set of observations will fall within a particular region, given the current posterior distribution.



