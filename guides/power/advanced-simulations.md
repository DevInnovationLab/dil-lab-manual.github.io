---
layout: default
title: Advanced topics - simulations
grand_parent: Guides
parent: Power calculations
nav_order: 6
---

## Calculating Power with Simulations

**As discussed before, the initial in power calculations should always be to use simple plug-in formulas.**
<!-- As soon as an experimental design gets a bit more complex, we would typically rely on our own simulations. -->
These analytical power calculations are useful for simple comparisons. 
**For nonparametric tests and more complex or more specific design choices, simulation-based power calculations provide more flexibility.**
They allow us to incorporate complex clustering and blocking schemes, as well as covariates, multiple treatment arms, and other refinements. 
They also have advantages when it comes to accounting for the multiplicity of testing if we want to test more than one null hypothesis.

<!-- The basic idea is to write down an equation that describes the data generating process (DGP) and treatment assignment, including an expected effect size. -->
<!-- This model will have a non-stochastic part (sample size, number of clusters, distribution of the sample across clusters, number of time periods, ICC, autocorrelation terms, mean and standard deviation of the outcome variable, effect size, etc) and a stochastic part (an error term). -->
<!-- We then simulate this DGP a few thousand times and simply count the number of times the treatment coefficient is statistically different from zero. -->
These simulations require us to specify the following:
- an underlying model
- the full experimental design
- the sample size
- the values of the covariates
- the parameter values expressing the distribution of the outcome variable under the alternative hypothesis
- the variances. 

**Based on the pre-specified model, we generate synthetic data and estimate the treatment effect on these data a large number of times. 
In each round of the simulations we obtain a p-value. 
Power is then calculated as the proportion of p-values that are lower than the desired cutoff value $\alpha$.**
For designs with clustered treatment assignment or blocked designs, it is important to cluster the standard errors appropriately, otherwise the t-statistics will be upward biased and we will obtain inflated power numbers.

As a starter, the most simple setup for a simulation is illustrated in the code snippet below.
It draws from two different distributions n-times, compares their means, and stores the t-statistic.
The share of significant results is then the power of our "design" (which is a clear overstatement for this simple example).
If the number of draws is sufficiently large, the power number here will correspond to the number that we determined above with the plug-in formula.


```
# Very basic example simulation

library(tidyverse)

## Define a function to test the difference in means and return the t-test value
get_t_result <- 
  function(sampleSize, mean_C, mean_T, sd) {
    
    # Simulate values for the outcome variable for both groups
    # Assuming a normal distribution with the same size and standard deviation in both groups
    group1 <- rnorm(sampleSize, mean_C, sd)
    group2 <- rnorm(sampleSize, mean_T, sd)
    
    # Test for different in means using a t-test
    # (could also run a regression and extract the t-stat or p-value)
    ttest.result <- t.test(group1, group2) 
    
    # Return the value of the t-stat 
    # (or equivalently the p-value)
    return(tibble(tstat = ttest.result$statistic)) 
  }

## Determine our input values
num_runs <- 1000 # Number of times the test will be run
sampleSize <- 30 # Sample size (this is the size of the control and the treatment groups separately, not the added total)
mean_C <- 30 # Control mean
mean_T <- 35 # Treatment mean
sd <- 50 # Standard deviation

## Test the difference in means repeatedly
# (Instead of looping, we use the apply() class of functions
# this is called vectorization in R and is strictly preferred due to its computational advantages()
tstats <- 
  map(
    1:num_runs, 
    ~ get_t_result(sampleSize, mean_C, mean_T, sd)
  )

# Count the number of t stats above 1.96
mean(abs(unlist(tstats)) > 1.96)
```

