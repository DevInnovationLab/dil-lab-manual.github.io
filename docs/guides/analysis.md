---
layout: default
title: Data analysis
parent: Data work guides
nav_order: 3
---

# Data analysis guide
{: .no_toc }

1. TOC
{:toc}

---

## Maintainable analysis code

For example, let’s say you are running regressions of multiple outcome variables on treatment assignment and a fixed set of controls. You could repeat yourself by writing the code to run one regression for each outcome variable, and list all controls on the code for each of these regressions. That means that if you wanted to add or remove a control variable, you would have to edit multiple lines of code. A more efficient way to do this would be to have a single representation of the set of control variables in your code, defining this set of variables in the main script (as a global macro in Stata or an object in R) and referring to it in analysis scripts. By doing this, you will be able to update all regressions by altering a single line in a single script.

The next step in reducing repetition in the same example would be to loop over outcome variables and write the code for the regressions only once.  An even more advanced example would be to create a function that runs the regression you are interested in, taking as input an outcome variable, and then loop that function on the multiple outcomes. Note that this option would also help partitioning your long scripts, as we recommended above, as the function itself could be saved in a separate script. 

