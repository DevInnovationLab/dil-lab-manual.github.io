---
layout: default
title: …and please don’t move anything
grand_parent: Principles of analytics
parent: Working with data
nav_order: 2
---

## ...and please don't move anything

The above principle of being comfortable touching data comes with an important qualifier: as a general rule, **data should never be modified directly**, regardless of the format it comes in, and changing data sets through any spreadsheet application should be completely avoided. Instead, it should be modified through code and changes should be saved in derived data sets. This will make data processing more transparent and reproducible.

This principle results in a hard rule for the storage of raw data: because it cannot be easily recreated, it should always be kept intact. **To avoid overwriting raw data, store it in a separate folder from derived datasets**. In the (extremely rare) case a file is saved in a format that cannot be edited through code, make as few changes manually as possible,  document all of them, and remember to save the modified version in a separate folder with a different name. A better solution is to save a version of the same data in a more accessible format as early as possible in your workflow and start treating this new file as the raw data.

For example, you may download data from a website in such a format that makes analyzing it with statistical software very difficult. Instead of opening it in Excel, making changes to it, and replacing the file, you should: (i) save the data as it was originally downloaded, (ii) load it in statistical software and write code making the desired changes, (iii) save the derived dataset in a separate folder from the original one. This will allow you and other people to tell which dataset was created by you and which one comes from an external source. It will also guarantee that even if the website goes offline, you still have access to the original data. Finally, it will create a record of what modifications were made to the original dataset.

[DIL data folder structure](https://github.com/DevInnovationLab/dil-template-repo/tree/main/data){: .btn .btn-more }{:target="_blank"}

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/show.md %}){: .btn .btn-more }
</span>

