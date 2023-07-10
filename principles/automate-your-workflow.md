---
layout: default
title: Automate your workflow from the start
grand_parent: Principles of analytics
parent: Writing code
nav_order: 7
---

## Automate your workflow from the start

We often include manual steps in our workflow, thinking we will only do something once or twice. However, we invariably end up doing it more often than anticipated. It is very likely that before submitting a paper you will need to prepare a reproducibility package – if not because the journal requires it, because you will want someone outside the project team to do at least a computational reproducibility check. Writing code to re-run years of work will be a daunting task. So do yourself a favor and **think about an automation workflow at the onset of your analytical work**. [It will save you a lot of time](https://xkcd.com/1205/){:target="_blank"} over the project’s life-cycle. There are two key steps to follow when setting up this workflow:

1. **Create a *main script* to run all the other scripts for a project**. It is easier to do this for projects that use a [single software](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start){:target="_blank"}, but it is also possible to use this script to run one software from another. There are functions to call R and Python from Stata, for example, and vice-versa. In the unlikely case it is not possible to write such a script, consider using a Makefile. If that is also not an option, you should at the very least have a README file that explains exactly how to run the code and in which order. 

2. **Automate the importing of code outputs such as tables and figures into final outputs such as papers and presentations**. A common practice that breaks the automation principle is to export graphs from statistical software, save them as images, and manually load them into a paper or presentation. This practice dangerously increases the likelihood that images will not be updated in the final document when making last minute changes. Fortunately, there are many tools to automate this step. One option is to use markdown documents in the same statistical software used for data processing and analysis. Another one is to create a Makefile to run not only your statistical code but also to compile any LaTeX documents -- making sure that if one exhibit changes, the latest version will be included in the final document. 

Learning how to use these tools can be time consuming, but remember that not everyone involved in a project needs to know all the nitty-gritty of this setup. The key take-away is to know what you should aim for and where to ask for help when it’s time to put it into practice.

[Quarto: dynamic documents in Python, R, Julia, and Observable](https://quarto.org/){: .btn .btn-more }{:target="_blank"}
[LaTeX manual](https://en.wikibooks.org/wiki/LaTeX){: .btn .btn-more }{:target="_blank"}
[Template main.R](https://github.com/DevInnovationLab/dil-template-repo/blob/main/main.R){: .btn .btn-more }{:target="_blank"}
[Template main.do](https://github.com/DevInnovationLab/dil-template-repo/blob/main/main.do){: .btn .btn-more }{:target="_blank"}
[Calling R from Stata](https://github.com/reifjulian/rscript){: .btn .btn-more }{:target="_blank"}
[Calling Stata from R](https://github.com/lbraglia/RStata){: .btn .btn-more }{:target="_blank"}
[Basics of makefiles](https://the-turing-way.netlify.app/reproducible-research/make/make-examples.html#makefile-no-1-the-basics){: .btn .btn-more }{:target="_blank"}
[Template project README](https://github.com/social-science-data-editors/template_README/blob/release-candidate/templates/README.md#instructions-to-replicators){: .btn .btn-more }{:target="_blank"}


<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/test.md %}){: .btn .btn-more }
</span>