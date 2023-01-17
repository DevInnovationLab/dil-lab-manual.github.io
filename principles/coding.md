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

As soon as you get some data, you will probably want to start exploring it. This is good! But figuring out how to prepare and analyze your data on the fly often results in a patchwork of code that quickly becomes hard to manage. To avoid ending up in this position, **start planning your analytic workflow early on -- ideally before any data is acquired**. (As discussed [in the data section](https://devinnovationlab.github.io/guides/principles/data.html#start-simple), setting up the analytics with simulated data will often enable you to do so.) **Do some research about which software can handle the most complex analytics processes your project will require**. For example, if you know you need to perform complex spatial operations, you should prefer R or Python to Stata, since they have more developed GIS libraries. If it is not at all possible to use a single software, research the options available to [automate](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start) the cross-software workflow.

Apart from choosing a software, try to identify in advance which information, tasks, packages, functions, etc., you will require. Identifying procedures that work for a project is a collaborative process. Discuss with other coworkers what you need, agree on an analysis plan, organize the data work on a [data map](https://dimewiki.worldbank.org/Data_Map), and *then* start wrangling the data. 

## Code should live forever

**What does it mean for code to "stay alive"? It means that *any other researcher* can run it *without errors* and obtain *consistent results***. To achieve this, code should be written to endure: plan your analytic workflow having in mind that it may be used again and again. It may seem otherwise, but implementing good practices as soon as you start writing code will save you time. It will also make coding more pleasant!

**A common practice that prevents code from staying alive is requiring a series of manual steps to run the code or re-create outputs**. For example, projects where one needs to open and run different pieces of code in a particular order, where code is typed directly into a software’s console, or where users need to copy-paste inputs from one software to another – copy-pasting from statistical software to word documents being the most common offense. To avoid this issue, follow the [guidelines on automation discussed below](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start).

**Another common practice that hinders endurance is neglecting transferability and creating code that only runs in one computer**. For example, by hard coding file paths or using libraries that are not installed on other machines. Strategies that can help prevent this include:

- *Sharing all the necessary operating system configurations alongside the code through containers*. This is the safest way to guarantee a smooth transfer between computers, but it can also be costly to set up and requires specific software for code to be reused. 
- *Making it easy to adjust file paths*.
- *Setting up a system to manage packages and user-written commands*, including the specific versions used. This can be done in Python using virtual environments, in R with the `renv` package, and in Stata by sharing the code for the command versions used. 

[Use of Docker containers for Reproducibility in Economics](https://aeadataeditor.github.io/posts/2021-11-16-docker){: .btn .btn-more }{:target="_blank"}
[Writing transferrable file paths](https://dimewiki.worldbank.org/File_path){: .btn .btn-more }{:target="_blank"}
[Python virtual environments](https://realpython.com/python-virtual-environments-a-primer/){: .btn .btn-more }{:target="_blank"}
[Introduction to renv](https://rstudio.github.io/renv/articles/renv.html){: .btn .btn-more }{:target="_blank"}

## Don't repeat yourself

There are many problems with repetitive code: it takes longer to read, is error-prone, and is hard to maintain. In computer science, the [DRY rule](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) states that **"every piece of knowledge must have a single, unambiguous, authoritative representation within a system"**. A good rule of thumb to implement this rule is that if you have copied and pasted a chunk of code more than twice, it should probably be turned into a *function* or a *loop*. [Abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)) is the key concept behind this principle: separate inputs that are context-specific from the general processes. The latter can typically be re-used in different contexts, as long as the context-specific inputs are provided. 

Say, for example, that you are running regressions of multiple outcome variables on treatment assignment and a fixed set of controls. You could repeat yourself by writing the code to run one regression for each outcome variable, and list all controls on the code for each of these regressions. Note that the outcome variable is specific to each regression, but the set of controls is stable for the whole project. Given this setup, if you wanted to add or remove a control variable, you would have to edit multiple lines of code. A more efficient way to do this would be to have a single representation of the set of control variables in your code, defining this set of variables in the main script (as a global macro in Stata or an object in R) and referring to it in analysis scripts. By doing this, you will be able to update all regressions by altering a single line in a single script. To go further, you could also loop over outcome variables and write the code for the regressions only once.

An extension of the DRY rule is to not spend time reinventing the wheel. **If you are trying to do something that does not seem easy to implement, spend some time looking for an existing function from reputed sources to do it**. Using canned functions will make your code easier to read and less buggy. Developers usually share their solutions in the form of packages or libraries which include extensive error-handling features that are not thought of when first implementing a task. For example, both R and Stata have commands that allow you to create a balance table with a single line of code, so writing code from scratch to summarize variables, test for differences in means, and organize this information into a table means repeating other people’s work, which is not a great use of your time.

## Be kind to your reader

Coding is a collaborative process with ourselves and others. Collaboration is only possible if there is a shared understanding between people and, more importantly, [over time](https://twitter.com/commitstrip/status/689153602254974976). Never trust your future self to simply remember what you know today, or [you may become your own worst enemy](http://www.threepanelsoul.com/comic/on-perl). To make things easier for [yourself](https://www.meme-arsenal.com/en/create/meme/4734358), **write your code as if it is going to be read by someone who doesn't have any context about it**. There are a million different ways to make code more readable, but here are a few basic ones:

### Style
- *Write short lines.* While different languages have different rules for the ideal script length, almost all style guides recommend not going beyond 80 characters in a line.
- *Write short, modular scripts.* One rule of thumb is to aim at having no more than 200 lines per file. Another one is that if you are loading data, this should be the start of a new script -- and if you are saving data, this should be the end of the current one.
- *Use a [style guide](https://xkcd.com/1513/).* For DIL projects, follow the style guides linked in the buttons below.
- *Use white space and indentation.* Youcanreadandunderstandasentenceevenwithoutspaces. But they sure make it a lot easier. Different languages have different standards for how to use spacing. Check the style guides linked above for recommendations. 

[Modular programming](https://www.tiny.cloud/blog/modular-programming-principle/){: .btn .btn-more }{:target="_blank"}
[DIME's Stata style guide](https://worldbank.github.io/dime-data-handbook/coding.html#the-dime-analytics-stata-style-guide){: .btn .btn-more }{:target="_blank"}
[Tidyverse's R style guide](https://style.tidyverse.org/){: .btn .btn-more }{:target="_blank"}
[PEP8 - Python style guide](https://peps.python.org/pep-0008/){: .btn .btn-more }{:target="_blank"}

### Content
- *Write self-documenting code as much as possible.* Name variables, files, directories, and functions intuitively (e.g., `temp` is a terrible name for both folders and files). We recommend avoiding blank spaces in file and directory names.
- *Make inputs explicit.*
- *Divide scripts into sections with self-explanatory header titles.* Both the Stata do-file editor and RStudio have built-in features for this.
- *Add comments to the code*: self-documentation can only go so far. Comments should explain not only *what* you are doing, but *why* you are doing it.
- *Add metadata on functionality, inputs, and outputs to your code.* The creation of documentation for functions is automated in R and Python, but this type of information is also important when writing data processing and analysis scripts. For the latter, include a header with information on the purpose of your code, what files it uses, and what files it creates.
- *Write a project readme and have a system to keep it updated.** Create the habit of updating the readme when you finish a task, open a pull request, or ask someone to review your code.

[Variable names in survey research](https://medium.com/@janschenk/variable-names-in-survey-research-a18429d2d4d8){: .btn .btn-more }{:target="_blank"}
[Naming files](http://www2.stat.duke.edu/~rcs46/lectures_2015/01-markdown-git/slides/naming-slides/naming-slides.pdf){: .btn .btn-more }{:target="_blank"}
[Naming functions](https://style.tidyverse.org/functions.html#naming){: .btn .btn-more }{:target="_blank"}
[Code headers in Stata](https://www.stata.com/new-in-stata/do-file-editor/){: .btn .btn-more }{:target="_blank"}
[Code folding and sections in RStudio](https://support.rstudio.com/hc/en-us/articles/200484568-Code-Folding-and-Sections-in-the-RStudio-IDE){: .btn .btn-more }{:target="_blank"}
[Function documentation in R](https://cran.r-project.org/web/packages/docstring/vignettes/docstring_intro.html){: .btn .btn-more }{:target="_blank"}
[Function documentation in Python](https://peps.python.org/pep-0257/){: .btn .btn-more }{:target="_blank"}
[Example of analysis script header](https://github.com/worldbank/rio-safe-space/blob/6b8907eefb430272100ea8de8db6e5d302ac7e58/Reproducibility%20Package/dofiles/analysis/paper/graphs/beliefs.do#L1-L13){: .btn .btn-more }{:target="_blank"}
[Template project readme](https://social-science-data-editors.github.io/template_README/){: .btn .btn-more }{:target="_blank"}
[Example of protocol to update readme](https://github.com/DevInnovationLab/dil-template-repo/blob/main/CONTRIBUTING.md#opening-a-pull-request-from-a-feature-branch-to-develop){: .btn .btn-more }{:target="_blank"}

## Track your changes

You already track changes to Word documents. You should also track changes to your code and data work. **Learn how to use git and start using it as soon as you start writing code**. Even in the unlikely case that you never need to go back and check previous versions of your files, it will still give you the peace of mind of knowing that if you break or erase something important, you can always go back.

There are many version control systems, but some are clearly better than others. Using file names to track changes, for example, is better than not tracking them at all. [But that can get unwieldy very quickly](https://twitter.com/nathanwpyle/status/971595282810130432). [Git](https://git-scm.com/) is the version control system most widely adopted among coders. It allows you to track changes to any plain text files, save incremental changes to your work, and compare different versions. It also creates incentives to document your work through commit messages. When combined with a hosting service like [GitHub](https://github.com/), it creates a workflow for multiple people to collaborate on a project simultaneously without breaking each other's codes, transfer code to different machines, track tasks and write documentation. **We recommend using GitHub to track changes to metadata (through codebooks), tables (by exporting them to plain-text files such as .tex and .csv), and figures as well as code, so you always know how changes in the code are affecting its outputs.** 

[Writing meaningful commit messages](https://reflectoring.io/meaningful-commit-messages/){: .btn .btn-more }{:target="_blank"}
[Using branches for simultaneous collaboration](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches){: .btn .btn-more }{:target="_blank"}
[Using GitHub for cloud syncing](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/keeping-your-local-repository-in-sync-with-github/syncing-your-branch){: .btn .btn-more }{:target="_blank"}
[Using GitHub issues to track tasks](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues){: .btn .btn-more }{:target="_blank"}
[About GitHub wikis](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis){: .btn .btn-more }{:target="_blank"}
[Tracking changes to images](https://github.blog/2011-03-21-behold-image-view-modes/){: .btn .btn-more }{:target="_blank"}

## Ask questions

Don't spend too much time banging your head against the wall, it is not a good use of your time. If you seek help, chances are you will find that others have had similar challenges and a solution already exists. To save everyone's time, however, you should **learn when, where and how to ask questions**. 

Your first resource should be looking for already existing answers: try pasting error messages on search engines and consulting help files. Answers to most questions can usually be found on Stack Overflow or some other users forum. **If you have spent about 15 minutes trying to find a similar question that has already been answered and did not succeed, then ask colleagues (use DIL's `#_analytics_help` Slack channel) or open a new question on [Stack Overflow](https://stackoverflow.com/). In these cases, the quality of the answer you will get tends to be directly proportional to the quality of your question**. Make sure to describe (i) what you would like to do, (ii) what result you are expecting, (iii) what you have already tried that did not work, (iv) the results or error messages you received when trying it, (v) your software version and system details. If possible, provide a reproducible example or mock dataset.

[Writing the perfect question](https://codeblog.jonskeet.uk/2010/08/29/writing-the-perfect-question/){: .btn .btn-more }{:target="_blank"}

## Automate your workflow from the start

We often include manual steps in our workflow, thinking we will only do something once or twice. However, we invariably end up doing it more often than anticipated. It is very likely that before submitting a paper you will need to prepare a reproducibility package – if not because the journal requires it, because you will want someone outside the project team to do at least a computational reproducibility check. Writing code to re-run years of work will be a daunting task. So do yourself a favor and **think about an automation workflow at the onset of your analytical work**. [It will save you a lot of time](https://xkcd.com/1205/) over the project’s life-cycle. There are two key steps to follow when setting up this workflow:

1. **Create a *main script* to run all the other scripts for a project**. It is easier to do this for projects that use a [single software](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start), but it is also possible to use this script to run one software from another. There are functions to call R and Python from Stata, for example, and vice-versa. In the unlikely case it is not possible to write such a script, consider using a Makefile. If that is also not an option, you should at the very least have a README file that explains exactly how to run the code and in which order. 

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

## Test your code continuously

Even small changes can introduce bugs into scripts that were previously working. The best way to prevent issues from snowballing into serious errors is to have a system to continuously test code and catch bugs. A simple practice that can help with this is **running the code from the top regularly to ensure every step in your project is still working** (if you code has been [automated](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start), this should as simple as pushing one button). A more advanced practice is to **write code to test your code**.
 
Two concepts from software development are particularly useful when it comes to best practices in testing code. The first one is [unit testing](https://tuskr.app/learn/unit-testing), that is, checking that each part of a script is not only running without throwing errors, but also consistently producing the desired results. The second is called [defensive programming](https://en.wikipedia.org/wiki/Defensive_programming), or the idea that your code should be able to handle unexpected input. Applications of these concepts to data processing and analysis use cases may not be immediately intuitive. One example is to write code that can detect extreme outliers and handle missing values or text with non-English characters. Another important practice is to test the output of data wrangling operations that often cause errors, for example checking the number of observations in the data after combining or aggregating data sets. 

## There's always more to learn

As with most skills, coding skills need to be maintained. One way to do it is to **read other people's code and have them read yours**. If we often ask others to review our emails before we send them, how come we don't ask them to read our code before presenting its results? If you don’t have people you can go to, you can still review your own code. In both cases, asking the following questions when reading a piece of code will help you improve it:

- What can go wrong in this code?
- Does this code make sense? Can it be simpler? Can it be made more efficient?
- Should this code chunk be a function? Or maybe an external file used as a function input?
- What happens if more observations are added to the data? And if some are removed?
- How many lines of code would I have to update if a research decision changed?

Reading help files and cheat sheets is also a great way to learn more about languages you already use. For example, there may be a faster command to do something that always took you a long time, or a function you were already using may have options you didn’t know about. **Cultivate the habit of checking the help file** when using a command – you will be positively surprised by what you can learn. Finally, **many efficiency gains will come from how you use your IDE**, so make sure to learn the shortcuts and workflows for your software of choice.

[RStudio shortcuts](https://appsilon.com/rstudio-shortcuts-and-tips/){: .btn .btn-more }{:target="_blank"}