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

Some researchers find it easy to write a lot of statistical modeling code while ignoring the underlying input data. The data is a key ingredient of research, so don't treat it as something distant and abstract. The only way to really get to know it is by looking at, handling, and probing it. While sometimes it is necessary to blind yourself to parts of data that you analyze to avoid bias, if you are not in that situation then as a default you should take an attitude of **working directly with the data**. 

**Browse and explore the data** to understand how variables are distributed, identify patterns, and spot problems. Do this before you start running regressions or specifying other models which will add more layers of abstraction between you and your data. Knowing the data well will make it easier to interpret and understand the results of more elaborate analysis. Some useful first steps when looking at data include 

- confirming the unit of observation, 
- creating summary statistics tables and distribution graphs, 
- inspecting outliers, and 
- investigating missing values.

By doing this you will often be able to spot potential irregularities in your inputs (indicating problems with data or a need to tweak your modeling approach), hypothesize data generating process (more on which below), and get a feeling for how to generalize from the present data into new contexts in the future.

## ...and please don't move anything

The above principle of being comfortable touching data comes with an important qualifier: as a general rule, **data should never be modified directly**, regardless of the format it comes in, and changing data sets through any spreadsheet application should be completely avoided. Instead, it should be modified through code and changes should be saved in derived data sets. This will make data processing more transparent and reproducible.

This principle results in a hard rule for the storage of raw data: because it cannot be easily recreated, it should always be kept intact. **To avoid overwriting raw data, store it in a separate folder from derived datasets**. In the (extremely rare) case a file is saved in a format that cannot be edited through code, make as few changes manually as possible,  document all of them, and remember to save the modified version in a separate folder with a different name. A better solution is to save a version of the same data in a more accessible format as early as possible in your workflow and start treating this new file as the raw data.

For example, you may download data from a website in such a format that makes analyzing it with statistical software very difficult. Instead of opening it in Excel, making changes to it, and replacing the file, you should: (i) save the data as it was originally downloaded, (ii) load it in statistical software and write code making the desired changes, (iii) save the derived dataset in a separate folder from the original one. This will allow you and other people to tell which dataset was created by you and which one comes from an external source. It will also guarantee that even if the website goes offline, you still have access to the original data. Finally, it will create a record of what modifications were made to the original dataset.



[Link button](http://example.com/){: .btn .btn-more }
