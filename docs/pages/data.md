---
layout: page
title: Working with data
nav_order: 3
---

# Working with data

## Touch whatever you want...

It is easy to write a lot of code and not even think about why we need it -- which almost always is to interact with the data. The data is a key ingredient of research, so don't treat it as something distant and abstract. While sometimes it is necessary to blind yourself to parts of data that you analyze to avoid bias, as a default take an attitude of **working directly on the data**: the only way to actually get to know it is by looking at, handling, and probing it. 

**Browse and explore the data** to understand how variables are distributed, identify patterns, and spot problems. Do this before you start running regression or specifying other models which will add more layers of abstraction between you and the data. Knowing your data well will make it easier to interpret and understand the results of more elaborate analysis. Some useful first steps when looking at data include 

- confirming the unit of observation;
- creating summary statistics tables and distribution graphs;
- inspecting outliers; and
- investigating missing values.

## ...and please don't move anything

The above principle of being comfortable touching data comes with an important qualifier: **data should never be modified directly, regardless of the format it comes in**. Changing datasets through any spreadsheet application should be completely avoided. Instead, they should be modified through code and changes should be saved as derived datasets. This is particularly important for raw data: because it cannot be easily recreated, it should be always kept intact. **To avoid overwriting raw data, it should be stored in a separate folder from derived datasets**. In the (extremely rare) case a file is saved in a format that cannot be edited through code, make as few changes manually as possible, make sure to document all of them, and remember to save the modified version in a separate folder with a different name. If possible, save a version of the same data in a more accessible format as soon as you can and start treating this new file as the raw data.

*For example*, you may download data from a website in such a format that makes analyzing it with statistical software very difficult. Instead of opening it in Excel, making changes to it and replacing the file, you should: (i) save the data as it was originally downloaded, (ii) load it in a statistical software and write code making the desired changes, (iii) save the derived dataset in a separate folder from the original one. This will allow you and other people to tell which dataset was created by you and which one comes from an external source. It will also guarantee that even if the website goes offline, you still have access to the original data. Finally, it will create a record of what modifications were made to the original dataset.
