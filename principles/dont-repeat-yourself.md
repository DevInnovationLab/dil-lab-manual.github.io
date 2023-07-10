---
layout: default
title: Don’t repeat yourself
grand_parent: Principles of analytics
parent: Writing code
nav_order: 3
---
## Don't repeat yourself

There are many problems with repetitive code: it takes longer to read, is error-prone, and is hard to maintain. In computer science, the [DRY rule](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself){:target="_blank"} states that **"every piece of knowledge must have a single, unambiguous, authoritative representation within a system"**. A good rule of thumb to implement this rule is that if you have copied and pasted a chunk of code more than twice, it should probably be turned into a *function* or a *loop*. [Abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)){:target="_blank"} is the key concept behind this principle: separate inputs that are context-specific from the general processes. The latter can typically be re-used in different contexts, as long as the context-specific inputs are provided. 

Say, for example, that you are running regressions of multiple outcome variables on treatment assignment and a fixed set of controls. You could repeat yourself by writing the code to run one regression for each outcome variable, and list all controls on the code for each of these regressions. Note that the outcome variable is specific to each regression, but the set of controls is stable for the whole project. Given this setup, if you wanted to add or remove a control variable, you would have to edit multiple lines of code. A more efficient way to do this would be to have a single representation of the set of control variables in your code, defining this set of variables in the main script (as a global macro in Stata or an object in R) and referring to it in analysis scripts. By doing this, you will be able to update all regressions by altering a single line in a single script. To go further, you could also loop over outcome variables and write the code for the regressions only once.

An extension of the DRY rule is to not spend time reinventing the wheel. **If you are trying to do something that does not seem easy to implement, spend some time looking for an existing function from reputed sources to do it**. Using canned functions will make your code easier to read and less buggy. Developers usually share their solutions in the form of packages or libraries which include extensive error-handling features that are not thought of when first implementing a task. For example, both R and Stata have commands that allow you to create a balance table with a single line of code, so writing code from scratch to summarize variables, test for differences in means, and organize this information into a table means repeating other people’s work, which is not a great use of your time.

<span class="fs-8">
[Next section]({{ site.baseurl }}{% link principles/be-kind-to-your-reader.md %}){: .btn .btn-more }
</span>