---
layout: default
title: Working with data
parent: Principles of analytics
---


# Working with data
{: .no_toc }

1. TOC
{:toc}

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

## ...and please don't move anything

The above principle of being comfortable touching data comes with an important qualifier: as a general rule, **data should never be modified directly**, regardless of the format it comes in, and changing data sets through any spreadsheet application should be completely avoided. Instead, it should be modified through code and changes should be saved in derived data sets. This will make data processing more transparent and reproducible.

This principle results in a hard rule for the storage of raw data: because it cannot be easily recreated, it should always be kept intact. **To avoid overwriting raw data, store it in a separate folder from derived datasets**. In the (extremely rare) case a file is saved in a format that cannot be edited through code, make as few changes manually as possible,  document all of them, and remember to save the modified version in a separate folder with a different name. A better solution is to save a version of the same data in a more accessible format as early as possible in your workflow and start treating this new file as the raw data.

For example, you may download data from a website in such a format that makes analyzing it with statistical software very difficult. Instead of opening it in Excel, making changes to it, and replacing the file, you should: (i) save the data as it was originally downloaded, (ii) load it in statistical software and write code making the desired changes, (iii) save the derived dataset in a separate folder from the original one. This will allow you and other people to tell which dataset was created by you and which one comes from an external source. It will also guarantee that even if the website goes offline, you still have access to the original data. Finally, it will create a record of what modifications were made to the original dataset.

[DIL data folder structure](https://github.com/DevInnovationLab/dil-template-repo/tree/main/data){: .btn .btn-more }{:target="_blank"}

## Show, don't (just) tell

Data speaks for itself. **Since researchers learn about the data by touching it, it is important to allow consumers of the research to have a similar experience**. This will typically help them understand the data being used and modeling assumptions. While all researchers make sure to tell their readers what methods were used to analyse data, it is less common to also show the inputs into models.

As a minimum, you should summarize analyzed data in tables and plot variables that are most important to the analysis. In addition, try to show a glimpse of the input data (a few rows of input into the model) in presentations or papers, especially if introducing new modeling methods or using atypical data structures. Often one look at “raw” inputs will immediately help the reader understand the “shape” of data (e.g. distributions of variables) and notational conventions you use. You can use either a snippet of the real anonymized dataset or a simulated dataset which best represents the real data.

**When preparing outputs, it’s important to know who your audience is**. Who you are presenting information to should determine how to share it. While some information can simply be shared over an email, donors and policy-makers will often expect a polished, stand-alone PDF. Conversely, notebooks are a great way to share both outputs and code for other researchers to review.
Whichever of these formats you choose, you will still need to decide whether a graph or a table are the best way to communicate different results and pieces of information in the data. **Before creating a table, ask yourself whether the information would be better presented as a graph – and vice-versa**. Exposure to good examples will make it easier for you to identify cases where understanding a message is difficult. So take note when you find either. 

**Presenting polished plots is key for any publication**. They will typically be a reader’s first interaction with the publication’s results, and therefore are an important aspect of how its message is communicated. However, creating good visual representations of data can be difficult, and it is a learned skill.  The resulting urge to neglect the fine-tuning of plots is only human, but **at least one person in any project team will need to take the time to learn the details of polishing graphical data**. This includes being able to modify characteristics of plots and tables such as dimensions, resolutions, and fonts, as well as rendering and exporting to different formats (including TeX, Word, PPT and also PDF/EPS). Make sure you identify the person on your team who can do this in the lead up to producing results.

[Table vs graph](https://www.storytellingwithdata.com/blog/2011/11/visual-battle-table-vs-graph){: .btn .btn-more }{:target="_blank"}
[**Internal** -- DIL templates for papers, memos, presentations and reports](https://github.com/DevInnovationLab/DIL-Templates){: .btn .btn-internal }{:target="_blank"}

## Start simple

Statistics is hard by itself, but simple models can take you very far. Economists know this better than other empiricists but still have a tendency to dote on complicated models. To avoid overcomplicating, start simple: when first interacting with your data **constrain the methods that are initially allowed and create a [minimum viable product](https://www.forbes.com/sites/theyec/2021/12/08/a-review-of-the-minimum-viable-product-approach/?sh=5f59d73d2e20) before adding bells and whistles**. Simplicity can be a feature, not a bug.
How this looks in practice will depend on how exploratory you are in your approach. However, it always makes sense to **build your model in stages of increasing complexity**, even if you're not planning to report on the intermediate steps (e.g. because you commited to your modeling choices by using a pre-analysis plan, which is a good thing). Examples include running a linear regression before more complicated methods, including only a few variables at a time, or running your model on 10% of the data first (especially if you have large dataset). When doing things in stages, you should not be concerned with obtaining "publishable" results: you want to do this because it will often help catch problems with data, coding, or even your chosen methods.

**A more ambitious but extremely useful approach to building models gradually is to work with fake data.** This is particularly apt when we are blinded to part of the data. We do this by assuming some "data generating process" (DGP), which is a function that generates datasets (typically with some noise!) and then programming your analytics to work with your DGP outputs. This approach has many advantages, including

1. testing performance of your methods (e.g., bias, precision, statistical power)
1. being able to program your analysis without waiting for data
1. checking your understanding of how your chosen statistical methods work "under the hood"

In cases where you know something about the problem, you can code a DGP without first looking at the data. Typically, however, you will use some existing data to design your DGP. For example, if studying an intervention meant to reduce child mortality in a country, you can typically find census data with geographical and temporal variation for that country. This information will allow you to simulate a realistic data structure (via resampling, adding noise, or just visually checking that your DGP matches census data) against which you can test your methods. Note as well that programming a DGP first will often help you spot problems in data from your research project. In our example, suppose the project-collected data for an indicator has a distribution which does not resemble that of the same indicator on the census (e.g., it has much higher mean or much lower variation). Then you may need to ask yourself if this indicator is defined consistently with other data sources, in what way your sample is representative, or hypothesise some necessary model adjustments.

## Create good data sets

Regardless of whether you start from the most complicated models or build them gradually and of whether you start by working on your project's data directly or using fake datasets, early on in every empirical study you will need to define how to format and store inputs. You should choose a format that makes it convenient to summarize and plot data, run models, and eventually report on results.

As Hadley Wickham put it, "tidy datasets are all alike, but every messy dataset is messy in its own way". **Good data sets should be as intuitive and easy to use as possible**. To make you are creating data sets that will be easy for you and other people to use, **keep your data in a tidy (normalized) format** as much as possible, **make sure all your data sets have clearly labeled keys**, and **maintain documentation describing your data sets** at every stage of data transformation. 

Basic data documentation should include a codebook with information on each variable and metadata on the entire dataset, including (i) file name (with file extension), (ii) a short description of the information contained in the data, (iii) the data source, (iv) the unit of observation and the name of the key that identifies it in the data, (v) information about the frequency of data collection, (vi) information about the dates/period covered by the data. A template documentation file can be found [here](https://github.com/DevInnovationLab/lab-manual/blob/data-readme/docs/template/data-readme.md){:target="_blank"}.

It often happens that analysis datasets are supplied by outside collaborators. In such cases, you may not have access to the underlying raw data, or it may be too time consuming to reconstruct the dataset from scratch. In these situations, we recommend that you consider these datasets your raw data, even if they have already been pre-processed. That means you should go through the same steps to check data quality, explore, document, and, if needed, wrangle the data as you would for any raw dataset. Follow up with the data provider to clarify any points that are unclear, and document any issues you find, even if you don't know what caused them or how they can be addressed.

[Hadley Wickham's "Tidy data" paper](https://vita.had.co.nz/papers/tidy-data.pdf){: .btn .btn-more }{:target="_blank"}
["Tidy data" chapter in R for Data Science](https://r4ds.had.co.nz/tidy-data.html){: .btn .btn-more }{:target="_blank"}
[Data set keys](https://dimewiki.worldbank.org/ID_Variable_Properties){: .btn .btn-more }{:target="_blank"}
[Template data documentation](https://devinnovationlab.github.io/guides/templates/data-readme.html){: .btn .btn-more }{:target="_blank"}

## Be mindful of sensitive data

Researchers have a responsibility to protect all human subjects participating in their studies. **Make sure to familiarize yourself with and implement all of the data privacy and security guidelines at your institution**. Regardless of institution-specific guidelines, most of us already have the habit of **removing sensitive information from datasets as soon as possible in our workflow and keeping it encrypted** even if that means it will take longer to access the files when needed. Nevertheless, one important practice that may slip our minds is to **never include confidential information in code, documentation and other files that may be shared in the future or do not follow the same secure storage protocols as the raw data**. For example, if you are writing code to correct information about one particular person in your data, make sure to use an anonymous key variable instead of including their names on the code. And if the only way to identify that person is through their name, save the input file containing the name in an encrypted folder to be loaded by the code instead of writing it directly on the script. 

[AEA Data Editor on coding for confidential data](https://aeadataeditor.github.io/posts/2022-04-13-coding-confidential){: .btn .btn-more }{:target="_blank"}
[R package for statistical disclosure control](https://sdcpractice.readthedocs.io/en/latest/sdcMicro.html){: .btn .btn-more }{:target="_blank"}
[**Internal** -- UChicago Sensitive Data Usage Guide](https://dataguide.uchicago.edu/){: .btn .btn-internal }{:target="_blank"}
