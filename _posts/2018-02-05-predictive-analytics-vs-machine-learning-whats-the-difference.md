---
title: Predictive Analytics vs Machine Learning - What's the Difference?
excerpt: "Are predictive analytics and machine learning the same thing? If they're not, what's the difference?"
layout: work-in-progress
toc: true
last_modified_at: 2018-02-05
categories: [Machine Learning, Predictive Analytics]
---

There's a strong temptation to equate "predictive analytics" and "machine learning". It's not uncommon to throw the terms around interchangeably, which signals that the two are strongly related.

But is there a *difference* that sometimes gets lost when we substitute one term for the other? If there *is* a difference, is it important to distinguish? Is it dangerous or misleading to use the terms as synonyms?

## Predictive Analytics:  A Method for Analysis
In [Breaking Down Data Analysis vs Data Analytics: A Look at the Suffix](https://www.dataday.life/data-analysis-vs-data-analytics-examining-suffix/), I reasoned that analytics essentially "denotes the body of facts… the knowledge about… the principles for: analysis. Analytics is about methodology. It’s about the approach to performing analysis. It’s the science of analysis."

In [What Types of Data Analysis Are There?](https://www.dataday.life/what-types-of-data-analysis-are-there/), I noted that predictive *analysis* is what you're doing when you analyze data in a way that can produce predictions of measurements for specific "units" within a population (as opposed to inferential analysis where the measurement predictions are made for the population as a whole).

Combining the two concepts of "analytics" and "predictive analysis" ought to lend us to a natural definition for predictive analytics.

> Predictive analytics refers to the principles and methods for making measurement predictions for specific "units" within a population.

Predictive analytics is concerned with the principles and methods for, say...

* Taking an individual customer from the population of a company's customer base, analyzing data about him/her, and predicting the liklihood that he/she will purchase a new product offering
* Taking a single house from the population of homes in a city or neighborhood, and predicting the selling price

## Machine Learning:  A Way to do Predictive Analytics



## The Difference
Predictive analytics and machine learning are not "the same". Predictive analysis exists at this "type of data analysis that *can be done*" level. Machine learning does not.

What is machine learning then?

Machine learning is *a way to do* predictive analytics. Machine learning is a means to another end, namely, to predict measurement(s) for specific "units"/individuals in a population, based on a sample data set from that population.

Predictive analytics seeks to make estimations about specific people (or specific animals or widgets or [whatever] the "unit" of interest is from your population of "units"). One of the goals is to figure out paterns from historical data and be able to say something about the *future*, based on how that yet-unknown event fits within the patterns detected from past observations.

We want to be able to ask things like, "Which specific customers are more likely to purchase [this product] if we run [this marketing campaign] targeted at them?" or "What is a likely selling price for [this house]?" or any number of other questions that [fit the pattern](https://www.dataday.life/patterns-and-key-words-of-predictive-analytics-questions/) for predictive analytics to provide the answer for.

Machine learning just happens to be *one way* to accomplish the goal of predictive analytics.

Here's an example:  

### The Goal vs The Means
The means to do something... the methods and strategies and ways we approach accomplishing a goal are not the same thing as the goal itself. They're two distinct things, aren't they?  

If I say, "My goal is to save $1000 by Christmas.", I could go about achieving that goal in a dozen ways.  I might begin a saving strategy that involves setting back about $83 / month, the goal and the strategy are two separate things.  I might take on a side project to earn extra money. In either case, the strategy *accomplishes* the goal.  Without the *goal*, the strategy has no clearly defined purpose.

Predictive analysis is the goal.  Machine learning is a strategy used to *accomplish* predictive analysis.  The former gives the *purpose*...the reason to *do* machine learning in the first place. The tools we use to perform predictive analysis are various - machine learning just happens to solve the data *scale* problem that previous generations of analysts didn't face.

## Before There Were Machines to Learn
Before there were machines, there were... *people*.

People (statisticians in particular) have been doing predictive analysis for decades, if not centuries. It may have taken longer and been more tedius and error-prone, but steps that are taken to figure out "the answer" in machine learning have been do-able by humans for a long time... they are not "new".

Sooooo... why "machine learning"? In short, it's a *scale* problem with modern data sets. The data sets of the 21st century are much larger than ever before in history. 

While it's *possible* for people to compute the outputs that a machine learning algorithm can produce, it's *unnecessary*.  Due to the scale of data in today's world, it's also insanely impractical for many data sets.

## They're Different -- So What?
So who cares if they're different?  Is it even an important distinction to make?  What's the harm in swapping in "machine learning" for "predictive analytics", or vice-versa?

One could make the argument that it only matters if you're OCD about terms.  My take on it is that "data science" is already this nebulous, vague, muddy-water field, so any effort we can make to be precise about our terms can help clarify what we mean is helpful.

Is it *harmful* to equate predictive analytics and machine learning? I suppose that depends on your view of how important it is to be clear and precise so as not to cause confusion.

Having to Google "Predictive analytics vs machine learning" is one clue that the water is already muddy enough.  Life and death may not be at stake, but I think it's *helpful* to develop the right mental model for all of these pieces to fit together in the world of data science.



