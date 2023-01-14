---
layout: default
title: Writing code
parent: Principles of analytics
---


# Writing code
{: .no_toc }

1. TOC
{:toc}

---

## Choose wisely

There are pros and cons to all the different statistical software available. At the start of any project, you will need to **make an intentional choice about which software to use**. You may think that you will save time by using the software you are already most familiar with and implementing one or two pieces of analysis that it can't handle on another software. However, this often proves more time-consuming when setting up a complete reproducibility workflow, as you need to conciliate data transferring, versioning, and automation across all the programs used. Instead, **it is best to rely on a single software for all the analytics in a project**. 

**Do some research about which software can handle the most complex analytics processes your project will require**. For example, if you know you need to perform complex spatial operations, you should prefer R or Python to Stata, since they have more developed GIS libraries. If it is not at all possible to use a single software, make sure to have a script that runs all the code from all the different software in the correct order. For example, you can write a single main script that [calls R from Stata](https://github.com/reifjulian/rscript) (or [vice-versa](https://github.com/lbraglia/RStata)), or use more sophisticated tools, such as [makefiles](https://the-turing-way.netlify.app/reproducible-research/make/make-examples.html#makefile-no-1-the-basics). 

As soon as you get some data, you will probably want to start exploring it. This is good! But figuring out how to prepare and analyze your data on the fly often results in a patchwork of code that quickly becomes hard to manage. To avoid ending up in this position, **start planning your analytic workflow early on -- ideally before any data is acquired**. (As discussed earlier, setting up the analytics with simulated data will often enable you to do so.) Apart from choosing a software, try to identify in advance which information, tasks, packages, functions, etc., you will require. Identifying procedures that work for a project is a collaborative process. Discuss with other coworkers what you need, agree on an analysis plan, organize the data work on a [data map](https://dimewiki.worldbank.org/Data_Map), and *then* start wrangling the data. 


## Be kind to your reader

Coding is a collaborative process with ourselves and others. Collaboration is only possible if there is a shared understanding between people and, more importantly, [over time](https://twitter.com/commitstrip/status/689153602254974976). Never trust your future self to simply remember what you know today, or [you may become your own worst enemy](http://www.threepanelsoul.com/comic/on-perl). To make things easier for [yourself](https://www.meme-arsenal.com/en/create/meme/4734358), **write your code as if it is going to be read by someone who doesn't have any context about it**. There are a million different ways to make code more readable, but here are a few basic ones:

### Style
- **Write short lines.** While different languages have different rules for the ideal script length, almost all style guides recommend not going beyond 80 characters in a line.
- **Write short, modular scripts.** One rule of thumb is to aim at having no more than 200 lines per file. Another one is that if you are loading data, this should be the start of a new script -- and if you are saving data, this should be the end of the current one.
- **Use a [style guide](https://xkcd.com/1513/).** For DIL projects, follow the style guides linked in the buttons below.
- **Use white space and indentation.** Youcanreadandunderstandasentenceevenwithoutspaces. But they sure make it a lot easier. Different languages have different standards for how to use spacing. Check the style guides linked above for recommendations. 

[Modular programming](https://www.tiny.cloud/blog/modular-programming-principle/){: .btn .btn-more }
[DIME's Stata style guide](https://worldbank.github.io/dime-data-handbook/coding.html#the-dime-analytics-stata-style-guide){: .btn .btn-more }
[Tidyverse's R style guide](https://style.tidyverse.org/){: .btn .btn-more }
[PEP8 - Python style guide](https://peps.python.org/pep-0008/){: .btn .btn-more }

### Content
- **Write self-documenting code as much as possible.** Name variables, files, directories, and functions intuitively (e.g., `temp` is a terrible name for both folders and files). We recommend avoiding blank spaces in file and directory names.
- **Make inputs explicit.**
- **Divide scripts into sections with self-explanatory header titles.** Both the Stata do-file editor and RStudio have built-in features for this.
- **Add comments to the code**: self-documentation can only go so far. Comments should explain not only *what* you are doing, but *why* you are doing it.
- **Add metadata on functionality, inputs, and outputs to your code.** The creation of documentation for functions is automated in R and Python, but this type of information is also important when writing data processing and analysis scripts. For the latter, include a header with information on the purpose of your code, what files it uses, and what files it creates.
- **Write a project readme and have a system to keep it updated.** Create the habit of updating the readme when you finish a task, open a pull request, or ask someone to review your code.

[Variable names in survey research](https://medium.com/@janschenk/variable-names-in-survey-research-a18429d2d4d8){: .btn .btn-more }
[Naming files](http://www2.stat.duke.edu/~rcs46/lectures_2015/01-markdown-git/slides/naming-slides/naming-slides.pdf){: .btn .btn-more }
[Naming functions](https://style.tidyverse.org/functions.html#naming){: .btn .btn-more }
[Code headers in Stata](https://www.stata.com/new-in-stata/do-file-editor/){: .btn .btn-more }
[Code folding and sections in RStudio](https://support.rstudio.com/hc/en-us/articles/200484568-Code-Folding-and-Sections-in-the-RStudio-IDE){: .btn .btn-more }
[Function documentation in R](https://cran.r-project.org/web/packages/docstring/vignettes/docstring_intro.html){: .btn .btn-more }
[Function documentation in Python](https://peps.python.org/pep-0257/){: .btn .btn-more }
[Example of analysis script header](https://github.com/worldbank/rio-safe-space/blob/6b8907eefb430272100ea8de8db6e5d302ac7e58/Reproducibility%20Package/dofiles/analysis/paper/graphs/beliefs.do#L1-L13){: .btn .btn-more }
[Template project readme](https://social-science-data-editors.github.io/template_README/){: .btn .btn-more }
[Example of protocol to update readme](https://github.com/DevInnovationLab/dil-template-repo/blob/main/CONTRIBUTING.md#opening-a-pull-request-from-a-feature-branch-to-develop){: .btn .btn-more }

## Track your changes

You already track changes to Word documents. You should also track changes to your code and data work. **Learn how to use git and start using it as soon as you start writing code**. Even in the unlikely case that you never need to go back and check previous versions of your files, it will still give you the peace of mind of knowing that if you break or erase something important, you can always go back.

There are many version control systems, but some are clearly better than others. Using file names to track changes, for example, is better than not tracking them at all. [But that can get unwieldy very quickly](https://twitter.com/nathanwpyle/status/971595282810130432). [Git](https://git-scm.com/) is the version control system most widely adopted among coders. It allows you to track changes to any plain text files, save incremental changes to your work, and compare different versions. It also creates incentives to document your work through commit messages. When combined with a hosting service like [GitHub](https://github.com/), it creates a workflow for multiple people to collaborate on a project simultaneously without breaking each other's codes, transfer code to different machines, track tasks and write documentation. **We recommend using GitHub to track changes to metadata (through codebooks), tables (by exporting them to plain-text files such as .tex and .csv), and figures as well as code, so you always know how changes in the code are affecting its outputs.** 

[Writing meaningful commit messages](https://reflectoring.io/meaningful-commit-messages/){: .btn .btn-more }
[Using branches for simultaneous collaboration](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches){: .btn .btn-more }
[Using GitHub for cloud syncing](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/keeping-your-local-repository-in-sync-with-github/syncing-your-branch){: .btn .btn-more }
[Using GitHub issues to track tasks](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues){: .btn .btn-more }
[About GitHub wikis](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis){: .btn .btn-more }
[Tracking changes to metadata]{: .btn .btn-more }
[Tracking changes to images](https://github.blog/2011-03-21-behold-image-view-modes/){: .btn .btn-more }

## Ask questions

Don't spend too much time banging your head against the wall, it is not a good use of your time. If you seek help, chances are you will find that others have had similar challenges and a solution already exists. To save everyone's time, however, you should **learn when, where and how to ask questions**. 

Your first resource should be looking for already existing answers: try pasting error messages on search engines and consulting help files. Answers to most questions can usually be found on Stack Overflow or some other users forum. **If you have spent about 15 minutes trying to find a similar question that has already been answered and did not succeed, then ask colleagues or open a new question on Stack Overflow. In these cases, the quality of the answer you will get tends to be directly proportional to the quality of your question**. Make sure to describe (i) what you would like to do, (ii) what result you are expecting, (iii) what you have already tried that did not work, (iv) the results or error messages you received when trying it, (v) your software version and system details. If possible, provide a reproducible example or mock dataset.

[Writing the perfect question](https://codeblog.jonskeet.uk/2010/08/29/writing-the-perfect-question/){: .btn .btn-more }
[DIL Slack channel for analytics help](){: .btn .btn-internal }