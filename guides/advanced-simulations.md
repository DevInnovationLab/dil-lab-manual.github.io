---
layout: default
title: Power through simulations
grand_grand_parent: Selected advanced topics
grand_parent: Coding guides
parent: Power calculations
nav_order: 66
---

## Calculating Power with Simulations

A first step in power calculations is always the usage of the plug-in formulas we saw above.
<!-- As soon as an experimental design gets a bit more complex, we would typically rely on our own simulations. -->
These analytical power calculations are useful for simple comparisons. For nonparametric tests and more complex or more specific design choices, simulation-based power calculations provide more flexibility. They for complex clustering and blocking schemes (i.e. stratification), can incorporate covariates, multiple treatment arms, etc. They also have advantages when it comes to accounting for the multiplicity of testing if we want to test more than one null hypothesis.

<!-- The basic idea is to write down an equation that describes the data generating process (DGP) and treatment assignment, including an expected effect size. -->
<!-- This model will have a non-stochastic part (sample size, number of clusters, distribution of the sample across clusters, number of time periods, ICC, autocorrelation terms, mean and standard deviation of the outcome variable, effect size, etc) and a stochastic part (an error term). -->
<!-- We then simulate this DGP a few thousand times and simply count the number of times the treatment coefficient is statistically different from zero. -->
These simulations require us to specify the following:
- an underlying model
- the full experimental design
- sample size
- the values of the covariates
- the parameter values expressing the distribution of the outcome variable under the alternative hypothesis
- the variances. 

Based on the pre-specified model, we generate our synthetic data and run the estimation on these data a large number of times. In each round of the simulations we obtain a p-value. Power is then calculated as the proportion of p-values that are lower than the desired cutoff value $\alpha$.

Note that we have to pay attention to cluster the standard errors appropriately for designs with clustered treatment assignment or blocked designs, otherwise the t-statistics will be upward biased and we will obtain inflated power numbers.

As a starter, the most simple setup for a simulation would be to just draw from two different distributions and compare their means - the same way we did initially with the two sample hypothesis testing.
The only thing we add is that we repeat this example n-times and store the t-statistic every time.
At the end we just count the number of significant comparisons. The share of significant results is then the power of our "design" (which is a clear overstatement for this simple example).

```
# very basic example simulation
# instead of looping, we use the apply() class of functions
# this is called vectorization in R and is strictly preferred due to its computational advantages

# define a function
get_t_result <- function(sampleSize, mean_C, mean_T, sd){
  sampleSize_C <- sampleSize_T <- sampleSize # 50/50 split
  # take sample for both groups, assuming a normal distribution
  # we assume the same sd for T and C
  group1 <- rnorm(sampleSize, mean_C, sd)
  group2 <- rnorm(sampleSize, mean_T, sd)
  # do a t.test (or a regression and extract the t-stat or p-value):
  ttest.result <- t.test(group1, group2) 
  # return the value of the t-stat (or equivalently the p-value):
  return(tibble(tstat = ttest.result$statistic)) 
}

sampleSize <- 30
num_runs <- 1000
mean_C <- 30
mean_T <- 35
sd <- 50
# Use apply to run the function n-times and store the t-statistics in a vector
tstats <- lapply(1:num_runs, function(x) get_t_result(sampleSize, mean_C, mean_T, sd))

# Count the number of tstats above 1.96
mean(abs(unlist(tstats)) > 1.96)

```

If the number of draws is sufficiently large, the power number here will correspond to the number that we determined above with the plug-in formula.
