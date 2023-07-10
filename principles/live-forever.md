---
layout: default
title: Code should live forever
grand_parent: Principles of analytics
parent: Writing code
nav_order: 2
---

## Code should live forever

**What does it mean for code to "stay alive"? It means that *any other researcher* can run it *without errors* and obtain *consistent results***. To achieve this, code should be written to endure: plan your analytic workflow having in mind that it may be used again and again. It may seem otherwise, but implementing good practices as soon as you start writing code will save you time. It will also make coding more pleasant!

**A common practice that prevents code from staying alive is requiring a series of manual steps to run the code or re-create outputs**. For example, projects where one needs to open and run different pieces of code in a particular order, where code is typed directly into a software’s console, or where users need to copy-paste inputs from one software to another – copy-pasting from statistical software to word documents being the most common offense. To avoid this issue, follow the [guidelines on automation discussed below](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start){:target="_blank"}.

**Another common practice that hinders endurance is neglecting transferability and creating code that only runs in one computer**. For example, by hard coding file paths or using libraries that are not installed on other machines. Strategies that can help prevent this include:

- *Sharing all the necessary operating system configurations alongside the code through containers*. This is the safest way to guarantee a smooth transfer between computers, but it can also be costly to set up and requires specific software for code to be reused. 
- *Making it easy to adjust file paths*.
- *Setting up a system to manage packages and user-written commands*, including the specific versions used. This can be done in Python using virtual environments, in R with the `renv` package, and in Stata by sharing the code for the command versions used. 

[Use of Docker containers for Reproducibility in Economics](https://aeadataeditor.github.io/posts/2021-11-16-docker){: .btn .btn-more }{:target="_blank"}
[Writing transferrable file paths](https://dimewiki.worldbank.org/File_path){: .btn .btn-more }{:target="_blank"}
[Python virtual environments](https://realpython.com/python-virtual-environments-a-primer/){: .btn .btn-more }{:target="_blank"}
[Introduction to renv](https://rstudio.github.io/renv/articles/renv.html){: .btn .btn-more }{:target="_blank"}

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/dont-repeat-yourself.md %}){: .btn .btn-more }
</span>