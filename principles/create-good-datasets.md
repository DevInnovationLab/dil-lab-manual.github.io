---
layout: default
title: Create good data sets
grand_parent: Principles of analytics
parent: Working with data
nav_order: 5
---

## Create good data sets

Regardless of whether you start from the most complicated models or build them gradually and of whether you start by working on your project's data directly or using fake datasets, early on in every empirical study you will need to define how to format and store inputs. You should choose a format that makes it convenient to summarize and plot data, run models, and eventually report on results.

As Hadley Wickham put it, "tidy datasets are all alike, but every messy dataset is messy in its own way". **Good data sets should be as intuitive and easy to use as possible**. To make you are creating data sets that will be easy for you and other people to use, **keep your data in a tidy (normalized) format** as much as possible, **make sure all your data sets have clearly labeled keys**, and **maintain documentation describing your data sets** at every stage of data transformation. 

Basic data documentation should include a codebook with information on each variable and metadata on the entire dataset, including (i) file name (with file extension), (ii) a short description of the information contained in the data, (iii) the data source, (iv) the unit of observation and the name of the key that identifies it in the data, (v) information about the frequency of data collection, (vi) information about the dates/period covered by the data. A template documentation file can be found [here](https://github.com/DevInnovationLab/lab-manual/blob/data-readme/docs/template/data-readme.md){:target="_blank"}.

It often happens that analysis datasets are supplied by outside collaborators. In such cases, you may not have access to the underlying raw data, or it may be too time consuming to reconstruct the dataset from scratch. In these situations, we recommend that you consider these datasets your raw data, even if they have already been pre-processed. That means you should go through the same steps to check data quality, explore, document, and, if needed, wrangle the data as you would for any raw dataset. Follow up with the data provider to clarify any points that are unclear, and document any issues you find, even if you don't know what caused them or how they can be addressed.

[Hadley Wickham's "Tidy data" paper](https://vita.had.co.nz/papers/tidy-data.pdf){: .btn .btn-more }{:target="_blank"}
["Tidy data" chapter in R for Data Science](https://r4ds.had.co.nz/tidy-data.html){: .btn .btn-more }{:target="_blank"}
[Data set keys](https://dimewiki.worldbank.org/ID_Variable_Properties){: .btn .btn-more }{:target="_blank"}
[Template data documentation](https://devinnovationlab.github.io/guides/templates/data-readme.html){: .btn .btn-more }{:target="_blank"}

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/mindful.md %}){: .btn .btn-more }
</span>