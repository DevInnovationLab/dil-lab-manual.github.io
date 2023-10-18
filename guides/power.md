---
layout: default
title: Power calculations
parent: Guides
has_children: true
has_toc: true
---


# Power calculations

We will first discuss a few general considerations regarding research design and statistical power and then, most importantly, illustrate what an ideal power calculation workflow in DIL projects looks like.
The most common research scenarios are being outlined and we'll see how power calculations change based on design choices.
**This note is accompanied by an interactive `Shiny` document which can be [accessed here](https://lehner.shinyapps.io/dil_power/) and is best used side-by-side to this note.**
**More advanced topics are only treated at a high level by providing basic intuition.**
**These are covered in detail with example code in separate notebooks which are hosted [on the main branch](https://github.com/DevInnovationLab/guides/tree/main) of the `guides` repository.**
If you have a good example code from your own project, please reach out so we can showcase it and help improve the quality of future DIL work.

When computing the needed sample size for an RCT, one of the most important questions we have to answer is what is the smallest difference in the average of the outcome variable between treatment and control group that we would like to be able to detect.
As a primer, we will quickly revisit conventional two-sample hypothesis testing in order to see the role effect size, $$\delta$$, and standard deviation of the outcome, $$\sigma$$, play in the process.