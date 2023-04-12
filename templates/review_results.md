---
layout: default
title: Review results and summary statistics tables
grand_parent: DIL templates
parent: Paper submission checklist
nav_order: 3
---

## Review results and summary statistics tables 

- [ ] All columns and rows clearly labeled.
  - [ ] Labels are understandable to someone unfamiliar with the project.
  - [ ] It is clear how values should be interpreted (for example, it is clear whether a higher value for an index is desirable or not).
- [ ] There are no unintentional line breaks and no text is cut-off.
- [ ] Formatting is consistent across all tables.
- [ ] The number of decimal cases shown makes sense for all the values displayed.
- [ ] Values in the table are consistent with the content they represent (for example, dummy/categorical variables should only take values between zero and one, variables like income and age should never be negative).
- [ ] Table titles are self-explanatory.
- [ ] All tables include basic information such as sample size and R*.
- [ ] The table notes contain all the necessary information for it to be understood as a self-standing exhibit, including
  - [ ] Variable definitions describing level of winsorization, imputation, definition of indexes, logs, etc.
  - [ ] Sample description (and explanation of why the number of observations is different across columns if that is the case).
  - [ ] Description of symbols used to indicate different levels of significance.
  - [ ] Description of how missing values and zeros are treated.


### Regression tables

- [ ] The magnitude of effects is clear (consider adding the sample or control mean).
- [ ] Test results for any conclusions mentioned in the text are included (such as equality between coefficients and significance of effects in subgroups).
- [ ] Only interpretable coefficients are shown (for example, for regressions with fixed effects, the constant is not included).
- [ ] Tables show standard errors rather than t-statistics.
- [ ] Methods used to calculate standard errors are described in the table notes.
- [ ] Control variables or fixed effects used are shown in the table or described in the botes.
- [ ] Weighting method used is described in the notes.
- [ ] The estimation procedure used is clearly indicated in the table, title or notes (e.g. OLS, probit, logit).

[More on reviewing regression outputs](https://blogs.worldbank.org/impactevaluations/crowd-sourced-checklist-top-10-little-things-drive-us-crazy-regression-output){: .btn .btn-more }{:target="_blank"}


<span class="fs-8">
[Next section]({{ site.baseurl }}{% link templates/review_graphs.md %}){: .btn .btn-more }
</span>