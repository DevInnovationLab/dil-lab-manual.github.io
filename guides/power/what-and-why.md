---
layout: default
title: What is statistical power and why does it matter
grand_parent: Guides
parent: Power calculations
nav_order: 2
---

## What is statistical power and why does it matter

### Defining statistical power

> Statistical power is defined as the probability, before a study is performed, that a particular comparison will achieve "statistical significance" at some predetermined level (typically a p-value below 0.05), given some assumed true effect size.
> A power analysis is performed by first hypothesizing an effect size, then making some assumptions about the variation in the data and the sample size of the study to be conducted, and finally using probability calculations to determine the chance of the p-value being below the threshold.

[Gelman, Hill, Vehktari (2020) Regression and Other Stories, Chapter 16]

First, it has to be clarified that null hypothesis significance testing (NHST) - and thus also statistical power - is a frequentist concept only[^1].
The question we want to answer is: **how large a sample do we have to collect in order to be reasonably sure of meeting the study objectives**?
Power calculations are not just useful for randomized evaluations, however, but also worth doing before we carry out studies on *purely observational data*.
Think of a scenario where an intervention or event has already happened, and we need to figure out whether it is worth the time and expense of collecting or trying to get access to data.
Power calculations are sometimes even worth doing on published/finished research.


<!-- As a next step in this chain of thought it is useful to have a personal heuristic in place to approximate a counterfactual benchmark, e.g. what sample size would the authors have needed, had the effect size been only half of the reported one. -->

### A useful Heuristic: "Sixteen S-squared over D-squared"

A rough approximation introduced by Lehr says that **for a two sample t-test with power 80% and significance level 5%, the required sample size can be approximated by $$n \approx 16 \frac{\sigma^2}{\delta^2}$$,** where $$\sigma$$ is the standard error of the variable of interest and $$\delta$$ the difference in means that we want to detect.

### Why underpowered studies are bad

<!-- From the CzList paper 2019 southern: - see also the JPAL document that was linked on WB DIME -->
Inference from low-powered studies is problematic for two main reasons.
First, by definition, adequate power is required to ensure that studies have a high likelihood of detecting a genuine effect. **Low power implies high rates of false negatives whereby the null hypothesis of "no effect" is not rejected, despite being false.**
This can arguably have impacts on the development of scientific knowledge: false negative results are less likely to be followed up than false positives, self-correction is less likely to occur in these cases.

Second, low power threatens the credibility of research findings through effect inflation because **in settings where standard errors are large, only those findings that by chance overestimate the magnitude of the effect will appear statistically significant and thus pass the threshold for discovery**. Effect inflation is therefore more severe in underpowered studies that are based on small samples in the presence of high measurement error. This problem is also known as the winner's curse or referred to as a Type M error (a term coined by Andrew Gelman). It is well-known that conditional on NHST, research findings from non-experimental data suffer from an upward bias because of a "file drawer problem" of non-significant studies that are not being published.

<!-- The third, less appreciated aspect of statistical power is its relation to false discoveries. -->
<!-- The connection becomes clear once we abandon the practice of treating a single finding that has achieved formal statistical significance as conclusive evidence, and instead consider a Bayesian framework of statistical inference whereby any individual study contributes to scientific knowledge insofar as it moves our priors regarding the existence of the effect/association in question. -->
<!-- In this framework, studies may be assessed on the basis of their positive predictive value (PPV): The poststudy probability (PSP) that a research finding that has achieved formal statistical significance is indeed true (Wacholder et al. 2004; Ioannidis 2005).39 The basic ingredients of this metric are the Type I and II error rates (α and β, respectively), together with π, the fraction of true associations among all associations tested in a given field. -->
<!-- We treat this fraction as our prior: The prestudy odds that the association in question is true (we discuss different ways to obtain priors later in this section). -->
<!-- The PSP is then defined as the share of true associations which are declared true ([1 − β]π) divided by the share of all associations which are declared true ([1 − β]π + α[1 − π]). -->
<!-- As shown in Equation 3 below (reproduced from Maniadis, Tufano, and List (2014)), the PSP depends on the power of a study (1 − β) in the following way: -->

**Keep in mind the following: a corollary from everything we covered so far is that if a study has a small sample size, it necessarily has to find a large effect in order to obtain a significant result (according to our frequentist hypothesis testing standards).**

[^1]: A Bayesian would think about power differently. In essence, instead of focusing on frequencies of rejecting a null hypothesis when an alternative is true, a Bayesian would consider the posterior distribution of a parameter given the data. The strength of evidence for or against particular parameter values is expressed in terms of probability distributions. To analogously assess "power," a Bayesian might consider the probability that a future observation or set of observations will fall within a particular region, given the current posterior distribution.



