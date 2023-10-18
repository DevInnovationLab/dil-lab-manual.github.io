---
layout: default
title: DIL standards
grand_parent: Guides
parent: Power calculations
nav_order: 1
---

## DIL standards 

**It is crucial that every project has a stand-alone file - ideally a notebook combining code and text - that showcases power calculations.**
Over its lifecycle, different RAs, RPs, and PIs will contribute to it.
It is thus essential that [coding principles are strictly followed](https://devinnovationlab.github.io/guides/principles/writing-code.html) as in any other piece of work.
Such a document will also help the team think clearly about research design and how to best communicate it at a very early stage.

This document should have two key features

- **The document must link to the folder or repository where the code is stored** so the reader can always access the latest version or the document. Ideally also push these reports to the GitHub repository of the respective project.
- **Every number mentioned in this report must be easily reproducible.** If there is no replication code, then the source of every number that was plugged into a formula must be stated clearly.

You can find some example notebooks in the [`power_calc/examples/` of this repository's main branch](https://github.com/DevInnovationLab/guides/tree/main).

### 1. Start with a quick abstract summary of descriptive statistics

The first task when performing power calculations is to gather intelligence on the three most fundamental pieces of information:

- **What is the expected mean of our variable of interest? How much do values deviate from this mean in reality?** Your document should start by indicating the mean and standard deviation of outcomes. 
- **What are the cluster sizes and estimates for intra-cluster correlation?** In case we want (or have) to assign treatment at a cluster or group level, we also need to gather information on the degree of similarity within each cluster or group.
This descriptive statistic is often referred to as the Intra-cluster Correlation Coefficient (ICC).
- **Which effect size can we expect roughly from our intervention?** To answer this question, refer to the relevant literature.

The relevant pieces of information can be gathered through a review of similar studies that were carried out in the past, the analysis of surveys and/or administrative data, or, ideally, a combination of the two. It is not advised to rely on pilot studies for power calculations due to small sample size problems.

### 2. Showcase simple power calculations from plug-in formulas

<!-- from csazr list 2019 translating critical values to optimal sample size requires knowledge of the variance of the outcome—a parameter unknown prior to conducting the experiment. This feature makes ex ante power calculations inherently hypothetical, as they are based on the researcher's expectations about the underlying data generating process (Gelman and Carlin 2014). -->

<!-- When deciding what effect size to target, researchers should consider what difference is actually practically or economically relevant—an aspect that is still largely overlooked both at the design and the inference stage.53 A useful practice is to express minimum detectable effect sizes in terms of standard deviation changes to facilitate comparison with existing studies in the field (e.g., the researcher may desire to have her experiment detect a 0.1 standard deviation treatment effect). -->

As a first step we always use basic plug-in formulas to get a rough sense for the needed sample size. This serves as a benchmark will be refined in the next step.

### 3. Incorporate more sophisticated designs

Using the plug-in formulas as a starting point, see how and why power increases when you refine the calculations by

- **Controlling for important covariates/predictors**. They usually soak up some of the variation in the variable of interest, reducing variance in the residuals of the regression and thus lowering the required sample size for any specified level of precision or power.
- **Using stratification/blocking**. These usually achieve similar gains in reducing variation.

For more complex settings, this last step is often done using simulation.
