---
title: "What is the tilde (~) \"symbol\" in R?"
author: "Andrew Bancroft"
date:   2019-04-30
description: "If you were to put words to what the tilde (~) symbol is in R, how would you explain it or interpret it? "
type: blog
draft: false
comments: true
wip: true
---

What is the tilde (`~`) "symbol" in R? 

If you were to put words to what it *is*, how would you explain it or interpret it?  

What does it mean (and therefore, what does it *do*)?

Here, I document a few of the unpackings that I've run across when it comes to `~` in R.

## From the Docs:  "y on x"
In the [R-project.org documentation](https://cran.r-project.org/doc/manuals/r-release/R-intro.html#Statistical-models-in-R), tilde `~` starts getting mentioned in chapter 11 when the discussion of "statistical models" begins.

So right away, one could glean that the `~` is used when trying to express a statistical model.

When [this variable] changes, [that one] responds.

When I nudge [this number], [that number] goes up (or down or stays the same).

Or at least we *think* so... The goal of a statistical model is to estimate an output (y) from one or more inputs (x's).  One thing we'd like to do is "model" the relationship of the variables using the data we've got, and use that model in the future on *new* data.

The way one *expresses* that modeled relationship in R is with `~`.

`y ~ x` for example might express a "linear regression model of y on x", according to the docs.

Interesting phrase... "y on x".

In other words, what we're saying is that "y responds to changes in x"... "values that come out (y's) depend on the various values that come in through x's".

`~` is a "definition" operator.  

What does it define? A formula for a statistical model.  It encapsulates all the inputs that are required to produce an estimated output of some sort.


https://stackoverflow.com/questions/14976331/use-of-tilde-in-r-programming-language

https://stackoverflow.com/questions/8055508/in-r-formulas-why-do-i-have-to-use-the-i-function-on-power-terms-like-y-i/8055683#8055683
