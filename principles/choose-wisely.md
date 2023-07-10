---
layout: default
title: Choose wisely
grand_parent: Principles of analytics
parent: Writing code
nav_order: 1
perma_link: "principles/"
---

## Choose wisely

There are pros and cons to all the different statistical software available. At the start of any project, you will need to **make an intentional choice about which software to use**. You may think that you will save time by using the software you are already most familiar with and implementing one or two pieces of analysis that it can't handle on another software. However, this often proves more time-consuming when setting up a complete reproducibility workflow, as you need to conciliate data transferring, versioning, and automation across all the programs used. Instead, **it is best to rely on a single software for all the analytics in a project**. 

As soon as you get some data, you will probably want to start exploring it. This is good! But figuring out how to prepare and analyze your data on the fly often results in a patchwork of code that quickly becomes hard to manage. To avoid ending up in this position, **start planning your analytic workflow early on -- ideally before any data is acquired**. (As discussed [in the data section](https://devinnovationlab.github.io/guides/principles/data.html#start-simple){:target="_blank"}, setting up the analytics with simulated data will often enable you to do so.) **Do some research about which software can handle the most complex analytics processes your project will require**. For example, if you know you need to perform complex spatial operations, you should prefer R or Python to Stata, since they have more developed GIS libraries. If it is not at all possible to use a single software, research the options available to [automate](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start){:target="_blank"} the cross-software workflow.

Apart from choosing a software, try to identify in advance which information, tasks, packages, functions, etc., you will require. Identifying procedures that work for a project is a collaborative process. Discuss with other coworkers what you need, agree on an analysis plan, organize the data work on a [data map](https://dimewiki.worldbank.org/Data_Map){:target="_blank"}, and *then* start wrangling the data. 

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/live-forever.md %}){: .btn .btn-more }
</span>