---
layout: default
title: Bad for power
grand_parent: Guides
parent: Power calculations
nav_order: 30
has_children: true
has_toc: true
---


## Important Aspects That Can Hurt Power

### Spillovers

Spillovers can lead to biased estimates of treatment effects.
Think of a scenario where the spillover effects on untreated individuals are positive.
The point estimate of the treatment dummy will generally be smaller than it would have been without spillovers.
The most straightforward solution to avoid complications stemming from spillovers is to refine the study design.
Randomizing at a cluster level and choosing clusters far apart from each other could be an obvious first step.
Sometimes we explicitly want to assess the degree of spillovers.
This could be done e.g. with a so-called saturation design where the treatment intensity is varied across clusters.
<!-- See @DufloGlennersterKremer2007 or @AtheyImbens2017 for a discussion on spillovers.
@Vazquez-Bare2022 offers a more specialized and up-to-date econometric treatment of spillover effects in RCTs.
 -->
### Budget/Money

The ex-ante optimal split between treatment and control arm is usually always 50/50.
When the cost to collect data from the control group is lower, it might make sense to collect more data from these non-treated units.
The optimal sampling ratio would then be proportional to the unit-costs in each arm.
<!--  see e.g. @DufloGlennersterKremer2007 for more details.
Chapter 6 of @McConnellVera-Hernandez2015 offers an even deeper dive, looking into heterogeneous costs etc. -->

### Takeup

Overly optimistic assumptions for the first stage can lead to a severely underpowered second stage.
For instance, to be powered to detect the same effect size with 25% take-up, we would need to offer treatment to 16 times more people and provide treatment to 8 times more people (assuming equal numbers of treatment and control) than if we had 100% take-up [(McKenzie 2011)](https://blogs.worldbank.org/impactevaluations/power-calculations-101-dealing-with-incomplete-take-up).
In some instances, take-up is less relevant than in others.
For example, sometimes the policy-relevant estimand is an intention to treat (ITT), i.e. the effect of treatment assignment and not treatment taken.
Regardless of what the estimand is, we always have to think carefully about how we can ensure high take-up rates and thus increase power and reduce costs.