---
layout: default
title: Be mindful of sensitive data
grand_parent: Principles of analytics
parent: Working with data
nav_order: 6
---

## Be mindful of sensitive data

Researchers have a responsibility to protect all human subjects participating in their studies. **Make sure to familiarize yourself with and implement all of the data privacy and security guidelines at your institution**. Regardless of institution-specific guidelines, most of us already have the habit of **removing sensitive information from datasets as soon as possible in our workflow and keeping it encrypted** even if that means it will take longer to access the files when needed. Nevertheless, one important practice that may slip our minds is to **never include confidential information in code, documentation and other files that may be shared in the future or do not follow the same secure storage protocols as the raw data**. For example, if you are writing code to correct information about one particular person in your data, make sure to use an anonymous key variable instead of including their names on the code. And if the only way to identify that person is through their name, save the input file containing the name in an encrypted folder to be loaded by the code instead of writing it directly on the script. 

[AEA Data Editor on coding for confidential data](https://aeadataeditor.github.io/posts/2022-04-13-coding-confidential){: .btn .btn-more }{:target="_blank"}
[R package for statistical disclosure control](https://sdcpractice.readthedocs.io/en/latest/sdcMicro.html){: .btn .btn-more }{:target="_blank"}
[**Internal** -- UChicago Sensitive Data Usage Guide](https://dataguide.uchicago.edu/){: .btn .btn-internal }{:target="_blank"}
