---
layout: default
title: Test your code continuously
grand_parent: Principles of analytics
parent: Writing code
nav_order: 8
---

## Test your code continuously

Even small changes can introduce bugs into scripts that were previously working. The best way to prevent issues from snowballing into serious errors is to have a system to continuously test code and catch bugs. A simple practice that can help with this is **running the code from the top regularly to ensure every step in your project is still working** (if you code has been [automated](https://devinnovationlab.github.io/guides/principles/coding.html#automate-your-workflow-from-the-start){:target="_blank"}, this should as simple as pushing one button). A more advanced practice is to **write code to test your code**.
 
Two concepts from software development are particularly useful when it comes to best practices in testing code. The first one is [unit testing](https://tuskr.app/learn/unit-testing){:target="_blank"}, that is, checking that each part of a script is not only running without throwing errors, but also consistently producing the desired results. The second is called [defensive programming](https://en.wikipedia.org/wiki/Defensive_programming){:target="_blank"}, or the idea that your code should be able to handle unexpected input. Applications of these concepts to data processing and analysis use cases may not be immediately intuitive. One example is to write code that can detect extreme outliers and handle missing values or text with non-English characters. Another important practice is to test the output of data wrangling operations that often cause errors, for example checking the number of observations in the data after combining or aggregating data sets. 

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/learn.md %}){: .btn .btn-more }
</span>