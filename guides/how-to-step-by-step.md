---
layout: default
title: How to perform power calculations for your project, step by step
grand_parent: Guides
parent: Power calculations
nav_order: 2
---

## How to Perform Power Calculations for your Project, Step by Step

First, we have to gather intelligence on the three most fundamental things:

-   What is the expected mean of our variable of interest?
-   How much do values deviate from this mean in reality?
-   Which effect size can we expect roughly from our intervention?

<!-- from csazr list 2019 translating critical values to optimal sample size requires knowledge of the variance of the outcome—a parameter unknown prior to conducting the experiment. This feature makes ex ante power calculations inherently hypothetical, as they are based on the researcher's expectations about the underlying data generating process (Gelman and Carlin 2014). -->

<!-- When deciding what effect size to target, researchers should consider what difference is actually practically or economically relevant—an aspect that is still largely overlooked both at the design and the inference stage.53 A useful practice is to express minimum detectable effect sizes in terms of standard deviation changes to facilitate comparison with existing studies in the field (e.g., the researcher may desire to have her experiment detect a 0.1 standard deviation treatment effect). -->

In case we want (or have) to assign treatment at a cluster or group level, we also need to gather information on the degree of similarity within each cluster or group.
This descriptive statistic is often referred to as the Intra-cluster Correlation Coefficient (ICC).

The relevant pieces of information can be gathered through a review of similar studies that were carried out in the past, the analysis of surveys and/or administrative data, or, ideally, a combination of the two.
It is not advised to rely on pilot studies for power calculations due to small sample size problems.

As a first step we always use basic plug-in formulas to get a rough sense for the needed sample size.
This serves as a benchmark and can/will be refined later by controlling for important covariates/predictors which usually soak up some of the variation in the variable of interest, reducing variance in the residuals of the regression and thus lowering the required sample size for any specified level of precision or power.
Similar gains can be achieved by stratification/blocking.
For more complex settings we usually want to resort to simulation methods in a final step.
This is something where we would recommend using R.

When computing the needed sample size for an RCT, one of the most important questions we have to answer is what is the smallest difference in the average of the outcome variable between treatment and control group that we would like to be able to detect.
As a primer, we will quickly revisit conventional two-sample hypothesis testing in order to see the role effect size, $\delta$, and standard deviation of the outcome, $\sigma$, play in the process.