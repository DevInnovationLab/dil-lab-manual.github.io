---
layout: default
title: A recap of hypoyhesis testing
grand_parent: Guides
parent: Power calculations
nav_order: 5
---

# Recapping Null Hypothesis Significance Testing (NHST)

Estimating whether an intervention - e.g. the treatment of an RCT - had an effect on the outcome is challenging due to sampling variation: the sample average of the treatment group will most of the time look different than the one of the control group due to chance alone.
<!-- The sample average of the treatment group will typically always look different than the one from the control group just because of sampling variation alone. -->
It is our task as researchers to assess whether this difference is large enough in order to conclude that it is due to actual differences at the population level - or whether it is too small and therefore most likely due to sampling noise alone.
That's where (frequentist) null hypothesis significance testing (NHST) enters.

We always start by stating the null hypothesis, $$H_0$$, which says that the effect was zero.
<!-- Typically we want to find evidence against it. -->
The alternative hypothesis, $$H_1$$, states that the effect was $$\delta$$ - the difference of the outcome variable between treatment and control group.
When conducting such a test, we can make two possible errors.
Rejecting a true null hypothesis, that is, to conclude that the intervention was effective when it was not (Type I error or "false positive").
We could also conclude that the intervention had no effect when in reality such an effect exists, i.e. fail to reject the null hypothesis when it is false (Type II error or "false negative").

|                        |    True Hypothesis (H0)     |    True Hypothesis (H1)     |
|------------------------|:---------------------------:|:---------------------------:|
| Test Decision (H0)     |      Correct Decision       | **Type II Error** [$$\beta$$] |
| *don't reject null*    |     (True Negative, TN)     |    (False Negative, FN)     |
| ---------------------- |   ----------------------    |   ----------------------    |
| Test Decision (H1)     | **Type I Error** [$$\alpha$$] |      Correct Decision       |
| *reject null*          |    (False Positive, FP)     |     (True Positive, TP)     |

When carried out on real-world data, we will never be able to know whether a Type I or Type II error is being committed.
We can, however, design our study as to control the probability of committing each type of error.

First, we have to define a significance level, $$\alpha$$.
This is conventionally set to 0.05 for a two-sided test and represents the probability of committing a Type I error ($$P[reject\ H_0\ |\ H_0\  true]$$).
This means that when the null is true, we won't reject it in 95% of cases.
Second, we have to make a choice on the probability of a Type II error, $$\beta$$ (not to be confused with the regression parameter below - notation was kept for consistency with most stats textbooks).
It refers to the chance of finding no treatment effect when one exists in reality ($$P[fail\ reject\ H_0\ |\ H_1\ true]$$).
The most common value for $$\beta$$ is 0.2.
Consequently, $$1-\beta$$ is the chance of finding an effect when it exists, i.e. the probability that a study has of uncovering a true effect.
**This is what we also call the (statistical) power of a test**.
Of course we would like power to be as high as possible, but usually a power of 80% (i.e. $$1-\beta = 0.8$$) is considered high enough.
Defining the two hypotheses, the desired significance level, and the power of the test, allows us to simultaneously control the likelihood of committing either a Type I or a Type II error.
By looking at the hypothetical distributions of the test statistic under the null and the alternative hypothesis, we obtain critical values for the test statistic corresponding to the pre-specified error rates.

<!-- shiny_hyptest on shinyapps companion here -->

The [companion Shiny app](https://lehner.shinyapps.io/dil_power/) illustrates the positive role a large effect size and a low deviation of the outcome have on power.


