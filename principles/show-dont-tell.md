---
layout: default
title: Show, don’t (just) tell
grand_parent: Principles of analytics
parent: Working with data
nav_order: 3
---

## Show, don't (just) tell

Data speaks for itself. **Since researchers learn about the data by touching it, it is important to allow consumers of the research to have a similar experience**. This will typically help them understand the data being used and modeling assumptions. While all researchers make sure to tell their readers what methods were used to analyse data, it is less common to also show the inputs into models.

As a minimum, you should summarize analyzed data in tables and plot variables that are most important to the analysis. In addition, try to show a glimpse of the input data (a few rows of input into the model) in presentations or papers, especially if introducing new modeling methods or using atypical data structures. Often one look at “raw” inputs will immediately help the reader understand the “shape” of data (e.g. distributions of variables) and notational conventions you use. You can use either a snippet of the real anonymized dataset or a simulated dataset which best represents the real data.

**When preparing outputs, it’s important to know who your audience is**. Who you are presenting information to should determine how to share it. While some information can simply be shared over an email, donors and policy-makers will often expect a polished, stand-alone PDF. Conversely, notebooks are a great way to share both outputs and code for other researchers to review.
Whichever of these formats you choose, you will still need to decide whether a graph or a table are the best way to communicate different results and pieces of information in the data. **Before creating a table, ask yourself whether the information would be better presented as a graph – and vice-versa**. Exposure to good examples will make it easier for you to identify cases where understanding a message is difficult. So take note when you find either. 

**Presenting polished plots is key for any publication**. They will typically be a reader’s first interaction with the publication’s results, and therefore are an important aspect of how its message is communicated. However, creating good visual representations of data can be difficult, and it is a learned skill.  The resulting urge to neglect the fine-tuning of plots is only human, but **at least one person in any project team will need to take the time to learn the details of polishing graphical data**. This includes being able to modify characteristics of plots and tables such as dimensions, resolutions, and fonts, as well as rendering and exporting to different formats (including TeX, Word, PPT and also PDF/EPS). Make sure you identify the person on your team who can do this in the lead up to producing results.

[Table vs graph](https://www.storytellingwithdata.com/blog/2011/11/visual-battle-table-vs-graph){: .btn .btn-more }{:target="_blank"}
[**Internal** -- DIL templates for papers, memos, presentations and reports](https://github.com/DevInnovationLab/DIL-Templates){: .btn .btn-internal }{:target="_blank"}

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/start-simple.md %}){: .btn .btn-more }
</span>