---
layout: default
title: Individual randomization
grand_parent: Coding guides
parent: Power calculations
nav_order: 11
---

## Individual Level Randomization


We will look at both continuous and binary outcomes when the treatment is assigned to individuals.
In the next section we will then look at these two cases when the treatment is assigned at a cluster or group level.
Everything else equal, this will lead to a decrease in power due to the non-independence of units within each group.
We therefore generally would prefer to design a study that allows us to randomize at the individual level.

### Continuous Outcomes

In order to test whether an RCT with simple randomization had a significant effect, in theory one does not even need a regression.
A simple difference in means by treatment status is unbiased for the average effect.
Since we want to introduce more sophisticated designs later in this short article, we introduce regression notation from the outset.
In order to obtain an average treatment effect, we just run the following univariate regression:

$$Y_i = \beta_0 + \beta_1 D_i + \varepsilon_i,$$ 

where $$D$$ is an indicator variable that indicates whether individual $$i$$ received the treatment or not.
$$\varepsilon$$ is an iid error term.
We are then interested in the hypothesis test of whether $$\beta_1$$ is different from zero.
<!-- The chosen significance level, i.e. the probability of rejecting the null hypothesis when it is in fact true (the so-called type I error rate), is typically assumed to be 5% for a two-sided test. -->
Writing down this hypothesis test formally, it is straightforward to derive a closed-form solution for the minimum detectable effect (MDE), given a sample size, and the required sample size, $$N^*$$, to detect a given difference in means, $$\delta$$.
We are interested in rejecting the null hypothesis $$H_0: \beta_1 = 0$$ in order show a significant effect of a treatment.

The standard deviation of the outcome is usually unknown and hence needs an estimation - or a best guess.
Sometimes this can be difficult.
We can either assume that the variance of the outcome is homogeneous across the treated and control group, and the standard deviation is $$\sigma$$, or we can assume that the variance is different for the two groups, and the standard deviations are $$\sigma_0, \sigma_1$$ respectively.
We only focus on the first case here.
The MDE that can be detected with $$1 − \beta$$ power at significance level $$\alpha$$ is 

$$\delta = \left(t_\beta + t_{\frac{\alpha}{2}}\right)\sigma\sqrt{\frac{1}{n_0}+\frac{1}{n_1}},$$ 

where $$n_0, n_1$$ are the sample size in the treatment and control group respectively.

Assuming that the sample size in the treatment and control groups are the same, $$n_0=n_1=n^*$$, the sample size needed for each group is $$n^* = 2\left(t_\beta + t_{\frac{\alpha}{2}}\right)^2\frac{\sigma^2}{\delta^2},$$ implying that the total sample size needed is $$N^* = 2n^*$$.
<!-- Under the second hypothesis of heterogeneous variance, the MDE that can be detected with $$1 − \beta$$ power at significance level $$\alpha$$ is --> <!-- $$\delta = \left(z_\beta + z_{\frac{\alpha}{2}}\right)\sqrt{\frac{\sigma_0^2}{n_0}+\frac{\sigma_1^2}{n_1}}$$ --> <!-- where $$\sigma_0, \sigma_1$$ are the standard deviation of the outcome variable $$Y$$ for the treatment and control groups respectively, and $$n_0, n_1$$ are the sample size in the treatment and control group respectively.  -->

<!-- The expression for the sample size is -->

<!-- $$N^* = \left(z_\beta + z_{\frac{\alpha}{2}}\right)^2\frac{1}{\delta^2}\left(\frac{\sigma_0^2}{\pi_0^*}+\frac{\sigma_1^2}{\pi_1^*}\right)$$ -->

<!-- where $$\pi_0^* = \frac{\sigma_0}{\sigma_0+\sigma_1}$$ and $$\pi_1^* = \frac{\sigma_1}{\sigma_0+\sigma_1}$$. The optimal allocation of the treatment and control group would be $$n_0^* = \pi_0^* N, n_1^* = \pi_1^* N$$. -->

In practice we will estimate MDE or sample size with the function `power.t.test()` (or alternatively with the corresponding function from the package `pwr`).
A good discussion of Stata equivalents can be found [in the DIME Wiki](https://dimewiki.worldbank.org/Power_Calculations_in_Stata).
In all of the above we implicitly assumed that the treatment has only an effect on the mean - which is by far the most common assumption and usually what we are interested in.
<!-- For cases where the treatment also affects the variance of the distribution for one group, see the discussion in @ListSadoffWagner2011 and @McConnellVera-Hernandez2015. -->

<!-- shiny app with individual - cont and binary with tabs? - HERE -->

### Binary Outcomes

For continuous outcomes, we do have to come up with an estimate for the standard deviation of the outcome variable.
Sometimes this can be difficult if little prior work exists and often a pilot is the only good way to get a good sense for how much the variable of interest is going to deviate.
Binary data is a bit more user-friendly, as the standard deviation is implied by the Bernoulli distribution, $$p*(1-p)$$, with the highest value at a base rate of 0.5.

To obtain the required sample size, we can measure the effect size in terms of differences in the probability of success: 

$$ N^{*}=\left(\frac{p_{1}\left(1-p_{1}\right)}{\pi}+\frac{p_{0}\left(1-p_{0}\right)}{1-\pi}\right) \frac{\left(z_{\beta}+z_{\alpha / 2}\right)^{2}}{\left(p_{1}-p_{0}\right)^{2}},$$ 

where $$p_{0}$$ is the probability of success or an event rate, and $$p_{1} = p_0 \times (1-MDE)$$.
$$\pi$$ represents the fraction of the sample that is treated and $$z$$ refers to the respective values from the standard normal distribution.

In practice, like in the continuous case, we can also use the built-in function `power.prop.test()`.


