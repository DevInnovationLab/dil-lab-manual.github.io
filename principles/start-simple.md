---
layout: default
title: Start simple
grand_parent: Principles of analytics
parent: Working with data
nav_order: 4
---

## Start simple

Statistics is hard by itself, but simple models can take you very far. Economists know this better than other empiricists but still have a tendency to dote on complicated models. To avoid overcomplicating, start simple: when first interacting with your data **constrain the methods that are initially allowed and create a [minimum viable product](https://www.forbes.com/sites/theyec/2021/12/08/a-review-of-the-minimum-viable-product-approach/?sh=5f59d73d2e20){:target="_blank"} before adding bells and whistles**. Simplicity can be a feature, not a bug.
How this looks in practice will depend on how exploratory you are in your approach. However, it always makes sense to **build your model in stages of increasing complexity**, even if you're not planning to report on the intermediate steps (e.g. because you commited to your modeling choices by using a pre-analysis plan, which is a good thing). Examples include running a linear regression before more complicated methods, including only a few variables at a time, or running your model on 10% of the data first (especially if you have large dataset). When doing things in stages, you should not be concerned with obtaining "publishable" results: you want to do this because it will often help catch problems with data, coding, or even your chosen methods.

**A more ambitious but extremely useful approach to building models gradually is to work with fake data.** This is particularly apt when we are blinded to part of the data. We do this by assuming some "data generating process" (DGP), which is a function that generates datasets (typically with some noise!) and then programming your analytics to work with your DGP outputs. This approach has many advantages, including

1. testing performance of your methods (e.g., bias, precision, statistical power)
1. being able to program your analysis without waiting for data
1. checking your understanding of how your chosen statistical methods work "under the hood"

In cases where you know something about the problem, you can code a DGP without first looking at the data. Typically, however, you will use some existing data to design your DGP. For example, if studying an intervention meant to reduce child mortality in a country, you can typically find census data with geographical and temporal variation for that country. This information will allow you to simulate a realistic data structure (via resampling, adding noise, or just visually checking that your DGP matches census data) against which you can test your methods. Note as well that programming a DGP first will often help you spot problems in data from your research project. In our example, suppose the project-collected data for an indicator has a distribution which does not resemble that of the same indicator on the census (e.g., it has much higher mean or much lower variation). Then you may need to ask yourself if this indicator is defined consistently with other data sources, in what way your sample is representative, or hypothesise some necessary model adjustments.

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/create-good-datasets.md %}){: .btn .btn-more }
</span>