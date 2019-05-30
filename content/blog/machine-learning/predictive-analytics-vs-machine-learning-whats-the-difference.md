---
title: "Predictive Analytics vs Machine Learning - What's the Difference?"
author: "Andrew Bancroft"
date:   2018-02-05
description: "Are predictive analytics and machine learning the same thing? If they are not, what is the difference?"
type: blog
draft: false
comments: true
aliases:
    - /predictive-analytics-vs-machine-learning-whats-the-difference/
---

There's a strong temptation to equate "predictive analytics" and "machine learning". It's not uncommon to throw the terms around interchangeably, which signals that the two are strongly related.

BUT. Is there a *difference* that sometimes gets lost when we substitute one term for the other? If there *is* a difference, is it important to distinguish?

## Predictive Analytics: A Method for Analysis
In [Breaking Down Data Analysis vs Data Analytics: A Look at the Suffix](https://www.dataday.life/data-analysis-vs-data-analytics-examining-suffix/), I reasoned that analytics essentially "denotes the body of facts… the knowledge about… the principles for: analysis. Analytics is about methodology. It’s about the approach to performing analysis. It’s the *science* of analysis."

In [What Types of Data Analysis Are There?](https://www.dataday.life/what-types-of-data-analysis-are-there/), I noted that predictive *analysis* is what you're doing when you analyze data in a way that can produce predictions of measurements for specific "units" within a population (as opposed to inferential analysis where the measurement predictions are made for the population as a whole).

Combining the two concepts of "analytics" and "predictive analysis" ought to lend us to a natural definition for "predictive analytics".

> Predictive analytics refers to the principles and methods for making measurement predictions for specific "units" within a population.

Predictive analytics is concerned with the principles and methods for, say...

* Taking an individual customer from the population of a company's customer base, analyzing data about him/her, and predicting the liklihood that he/she will purchase [this product] if we run [this marketing campaign] targeted at them
* Taking a single house from the population of homes in a city or neighborhood, and predicting the selling price

Predictive analytics encapsulates the principles and methods for computing estimations for these measurements (or any number of others that [fit the pattern of questions](https://www.dataday.life/patterns-and-key-words-of-predictive-analytics-questions/) for predictive analytics to provide the answer for).

The thing about "predictive analytics" as a term, is that it's pretty abstract.  Notably missing in these "principles and methods" is the **how to do it**.

*That* is what "machine learning" is.

## Machine Learning:  A Way to do Predictive Analytics
Machine learning is a way to *do* predictive analytics.

It is one way to take this idea of predicting measurements for an "individual unit" within a population, and turn it into a reality.

*One* way?  So... there are *other ways* to do predictive analytics??

I can think of at least one...

## Before There Were Machines to Learn
Before there were machines, there were... *people*.

People (statisticians in particular) have been doing predictive analysis for decades, if not centuries. It may have taken longer and been more tedius and error-prone, but steps that are taken to figure out "the answer" in machine learning have been do-able by humans for a long time... they are not "new".

Sooooo... why "machine learning"? 

In short, it's a *scale* problem with modern data sets. The data sets of the 21st century are much larger than ever before in history. 

While it's *possible* for people to compute the outputs that a machine learning algorithm can produce, it's *unnecessary*.  Due to the scale of data in today's world, it's also insanely impractical for many data sets.

## Automating the Human's Steps
If you handed me a small data set and said, "Manually find a way to produce a predicted house price for a home in [this neighborhood]", I could probably swing it.

If you handed me another similar data set and asked me to do the same thing, I could probably do it again, assuming I remember all the steps.  On the second round, I might even be brilliant enough to *write the steps down*. 

If you came to me again (and again, and again), I could follow the steps one by one to produce predictions.  I'd just be really tired, bored, and annoyed.

Naturally, you might ask, "Why not *automate the steps*?"

That's the idea behind machine learning!

"Machine learning" simply describes what computers do when they execute *programs* to produce predictions.

Computer scientists take the specific steps that need to be followed in order to produce a prediction (an *algorithm*, if you will) and *write code* to let a computer (a *machine*) do those steps and produce the prediction.

Same results.  Without goof-ups.  Faster.  

Happier Andrew.

That is machine learning... it involves the encoding of the steps that need to be taken in order to produce measurement predictions of all kinds in such a way that a computer can *execute* those steps and produce the result we want.

## The Bottom-Line
Predictive analytics and machine learning are not "the same". 

Predictive analytics is about [the way(s)], in general, to make estimations about specific people (or specific animals or widgets or [whatever] the "unit" of interest is from your population of "units"). 

Machine learning *is* one of those ways to make those predictions a reality.

The means to do something...the methods and strategies and ways we approach accomplishing a goal...are not the same thing as the goal itself. They're two distinct things, aren't they?  

If I say, "My goal is to save $1000 by Christmas.", I could go about achieving that goal in a dozen ways.  I might begin a saving strategy that involves setting back about $83 / month, the goal and the strategy are two separate things.  I might take on a side project to earn extra money, or sell stuff on Craigslist. In either case, the strategy *accomplishes* the goal.

Predictive analytics is the goal.  Machine learning is a strategy used to *accomplish* the goal.

## They're Different -- So What?
So who cares if they're different?  Is it even an important distinction to make?  What's the harm in swapping in "machine learning" for "predictive analytics", or vice-versa?

One could make the argument that it only matters if you're OCD about terms.  My take on it is that "data science" is already this nebulous, vague, muddy-water field, so any effort we can make to be precise about our terms can help clarify what we mean is helpful.

Is it *harmful* to equate predictive analytics and machine learning? I suppose that depends on your view of how important it is to be clear and precise so as not to cause confusion.

Having to Google "Predictive analytics vs machine learning" is one clue that the water is already muddy enough.  Life and death may not be at stake, but I think it's *helpful* to develop the right mental model for all of these pieces to fit together in the world of data science.



