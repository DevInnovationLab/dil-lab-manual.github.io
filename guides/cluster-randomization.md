---
layout: default
title: Cluster randomization
grand_parent: Guides
parent: Power calculations
nav_order: 12
---

## Cluster/Group Level Randomization

Individual randomization is typically preferred because of its statistical properties.
Often it is not feasible, though, so we are forced to allocate treatment at a higher level of aggregation.
Cluster randomized experiments allocate treatments to groups, but measure outcomes at the level of the individuals that compose the groups.

The estimating equation therefore changes to:

$$Y_{ij} = \beta_0 + \beta_1 D_j + v_j + \varepsilon_{ij},$$ 

where $$j$$ now denotes the cluster at which the treatment gets assigned (e.g. a village, health facility, classroom, ...).
Note that $$v_j$$ is an error term at the cluster level.
The two variances are given by $$var(v_j) = \sigma^2_c$$ and $$var(\varepsilon_{ij}) = \sigma^2_p$$.
These represent the variation of the outcome $$Y$$ at two different levels, group and individual (index $$p$$ stands for "personal" since $$i$$ is already in use).
Combining them we get $$\sigma^2_c + \sigma^2_p = \sigma^2$$.

For cluster studies we need to come up with a measure that determines the proportion of the total variance accounted for by the between cluster variance component, i.e. how much of the variance is explained by the clusters alone.
This so-called Intra-cluster Correlation Coefficient (ICC) gives us a measure of how similar units within each clusters are.
It has to be taken either from a large pilot, prior studies, or, in fortunate situations from large scale administrative or survey data.
Quite often coming up with reliable estimates for the ICC can be very challenging because large sample sizes are needed.
Since it can have huge effects on required sample sizes - especially when the cluster size is large - it is often worth performing power calculations with a variety of ICC levels to get a range of required sample sizes. [See the DIL article on ICC for further details].
The ICC is a summary statistic that is defined as:

$$\rho = \frac{\sigma^2_c}{\sigma^2_c + \sigma^2_p}.$$

The general implication of ICC for power calculations is that every additional individual adds less power the higher the ICC is.
A large ICC means there is a high degree of similarity of units within each cluster.
As a consequence, less information is added by each individual.
Adapting the formula involves some tedious algebra, but is generally straightforward.

### Continuous

The MDE changes to:

$$\delta = \left(t_\beta + t_{\frac{\alpha}{2}}\right) 2 \biggl( \frac{m \sigma^2_c + \sigma^2_p}{m k} \biggr),$$

where there are $$m$$ individuals in every cluster and the total number of clusters is $$k$$.
It is straightforward to adjust these calculations to allow for varying clustersizes.
Usually this is done by providing the coefficient of variation in clustersize across all clusters.
A large difference in clustersize generally decreases power, or, keeping power constant, increases the needed sample size to detect an effect.

In a similar fashion, the required sample size per treatment arm - assuming equal allocation - $$n^* = m^* \ k^*$$ becomes:

$$n^* = 2\left(t_\beta + t_{\frac{\alpha}{2}}\right)^2\frac{\sigma^2}{\delta^2} \ (1 + (m-1) \rho).$$

### Binary

For simplicity we abstract from differences in cluster sizes here again, but accommodating this in the formulas is quite straightforward (a high variation would further reduce power).

$$ N^{*}=\left(\frac{p_{1}\left(1-p_{1}\right)}{\pi}+\frac{p_{0}\left(1-p_{0}\right)}{1-\pi}\right) \frac{\left(z_{\beta}+z_{\alpha / 2}\right)^{2}}{\left(p_{1}-p_{0}\right)^{2}} \ (1 + (m-1) \rho).$$

Comparing this with the formulas for individual randomization from above, note that the only difference is the so-called **design effect**, sometimes called the variance inflation factor (VIF).
It is easy to see that the cluster randomization formulas nest the individual formulas (by setting the cluster size to 1).

Experiment with the [companion Shiny app](https://lehner.shinyapps.io/dil_power/) to see how detrimental ICC is for power.

