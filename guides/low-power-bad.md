---
layout: default
title: Why underpowered studies are bad
grand_parent: Coding guides
parent: Power calculations
nav_order: 4
---

# Why Underpowered Studies are Bad

<!-- From the CzList paper 2019 southern: - see also the JPAL document that was linked on WB DIME -->
Inference from low-powered studies is problematic for two main reasons.
First, by definition, adequate power is required to ensure that studies have a high likelihood of detecting a genuine effect. Low power implies high rates of false negatives whereby the null hypothesis of "no effect" is not rejected, despite being false.
This can arguably have impacts on the development of scientific knowledge: false negative results are less likely to be followed up than false positives, self-correction is less likely to occur in these cases.

Second, low power threatens the credibility of research findings through effect inflation because in settings where standard errors are large, only those findings that by chance overestimate the magnitude of the effect will appear statistically significant and thus pass the threshold for discovery. Effect inflation is therefore more severe in underpowered studies that are based on small samples in the presence of high measurement error. This problem is also known as the winner's curse or referred to as a Type M error (a term coined by Andrew Gelman). It is well-known that conditional on NHST, research findings (from non-experimental data) suffer from an upward bias (because of a "file drawer problem" of non-significant studies that are not being published) and there are ways to correct for this (e.g. a procedure by Andrews and Kasy).

<!-- The third, less appreciated aspect of statistical power is its relation to false discoveries. -->
<!-- The connection becomes clear once we abandon the practice of treating a single finding that has achieved formal statistical significance as conclusive evidence, and instead consider a Bayesian framework of statistical inference whereby any individual study contributes to scientific knowledge insofar as it moves our priors regarding the existence of the effect/association in question. -->
<!-- In this framework, studies may be assessed on the basis of their positive predictive value (PPV): The poststudy probability (PSP) that a research finding that has achieved formal statistical significance is indeed true (Wacholder et al. 2004; Ioannidis 2005).39 The basic ingredients of this metric are the Type I and II error rates (α and β, respectively), together with π, the fraction of true associations among all associations tested in a given field. -->
<!-- We treat this fraction as our prior: The prestudy odds that the association in question is true (we discuss different ways to obtain priors later in this section). -->
<!-- The PSP is then defined as the share of true associations which are declared true ([1 − β]π) divided by the share of all associations which are declared true ([1 − β]π + α[1 − π]). -->
<!-- As shown in Equation 3 below (reproduced from Maniadis, Tufano, and List (2014)), the PSP depends on the power of a study (1 − β) in the following way: -->

Keep in mind the following: a corollary from everything we covered so far is that if a study has a small sample size, it necessarily has to find a large effect in order to obtain a significant result (according to our frequentist hypothesis testing standards).
