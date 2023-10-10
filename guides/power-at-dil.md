---
layout: default
title: Power calculations at DIL
grand_parent: Guides
parent: Power calculations
nav_order: 1
---

## Guidelines for a DIL Powercalculation Summary Document

It is crucial that every project has a standing file - ideally a notebook combining code and text - that showcases power calculations.
Over its lifecycle, different RAs, RPs, and PIs will contribute to it.
It is thus essential that [coding principles are strictly followed](https://devinnovationlab.github.io/guides/principles/writing-code.html) as in any other piece of work.
Such a document will also help the team think clearly about research design and how to best communicate it at a very early stage.

-   Always start with a quick abstract summary of descriptive statistics: mean and standard deviation of outcomes, cluster sizes, estimates for the intra-cluster correlation, and expected effect sizes (with references to the respective literature).
-   Showcase simple power calculations from plug-in formulas first.
-   Using these as benchmarks, incorporate more sophisticated designs only afterwards and see how and why power increases (often this has to be done through simulations).
-   Always link to the folder/repository where the code is stored so anyone can always have a look at the latest, up-to-date version (ideally also push these reports to the Github repository of the respective project).
-   Every number has to be easily reproducible. If there is no replication code, then every number that was plugged into a formula has to be stated clearly.

You can find some example notebooks in the `power_calc/examples/` folder following [this link (main branch of guides repo)](https://github.com/DevInnovationLab/guides/tree/main).

