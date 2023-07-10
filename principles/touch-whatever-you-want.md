---
layout: default
title: Touch whatever you want...
grand_parent: Principles of analytics
parent: Working with data
nav_order: 1
---

## Touch whatever you want...

Some researchers find it easy to write a lot of statistical modeling code while ignoring the underlying input data. The data is a key ingredient of research, so don't treat it as something distant and abstract. The only way to really get to know it is by looking at, handling, and probing it. While sometimes it is necessary to blind yourself to parts of data that you analyze to avoid bias, if you are not in that situation then as a default you should **take an attitude of working directly with the data**. 

**Browse and explore the data to understand how variables are distributed, identify patterns, and spot problems**. Do this before you start running regressions or specifying other models which will add more layers of abstraction between you and your data. Knowing the data well will make it easier to interpret and understand the results of more elaborate analysis. Some useful first steps when looking at data include 

- confirming the unit of observation, 
- creating summary statistics tables and distribution graphs, 
- inspecting outliers, and 
- investigating missing values.

By doing this you will often be able to spot potential irregularities in your inputs (indicating problems with data or a need to tweak your modeling approach), hypothesize data generating process (more on which below), and get a feeling for how to generalize from the present data into new contexts in the future.

[R packages for exploratory data analysis](https://arxiv.org/pdf/1904.02101.pdf){: .btn .btn-more }{:target="_blank"}


<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/and.md %}){: .btn .btn-more }
</span>