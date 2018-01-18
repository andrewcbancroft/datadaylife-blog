---
title: Predictive Analytics vs Machine Learning - What's the Difference?
excerpt: "Are predictive analytics and machine learning the same thing? If they're not, what's the difference?"
layout: work-in-progress
toc: true
last_modified_at: 2018-01-18
categories: [Machine Learning, Predictive Analytics]
---

There's a strong temptation to equate "predictive analytics" and "machine learning". It's not uncommon to throw the terms around interchangeably, which signals that the two are strongly related.

But is there a *difference* that sometimes gets lost when we substitute one term for the other? If there *is* a difference, is it important to distinguish? Is it dangerous or misleading to use the terms as synonyms?

## Questions -> Data -> Analysis -> Answers
This flow is what it's all about, isn't it?  At the end of the day, you want *answers* so that you can take informed action.

But before you can get **answers**, you need to do a certain kind of **analysis**.

But before you do *analysis*, you need **data** to perform the analysis on.

But before you bother with *data*, you typically have **questions** in mind.  

You're curious about the world, your industry, your process. You make observations and you wonder if doing [something] will impact or *change* [something else] in a way that would lead to [some goal]. 

In order to satisfy your curiosity, you collect [data](https://www.dataday.life/what-is-data-like-im-five/) in the form of [quantitative](https://www.dataday.life/what-is-data-like-im-five/#quantitative-numerical) and [qualitative](https://www.dataday.life/what-is-data-like-im-five/#qualitative-categorical) measurements. 

The data fuels the possibility for analysis, so that hopefully, you walk away with a more complete picture than you had before (ie, you have answers).

## Types of Data Analysis
There are at least six kinds of analysis that can be performed on a data set:

1. Descriptive Analysis
2. Exploratory Analysis
3. Inferential Analysis
4. Predictive Analysis
5. Causal Analysis
6. Mechanistic Analysis

I've made [more detailed observations](https://www.dataday.life/what-types-of-data-analysis-are-there/) about each one of these six categories of analysis separately.  What I want you to notice about the list above is what *is* and *isn't* listed.

"Predictive Analysis" made the list at #4, but "Machine Learning" didn't.  Why?

## The Difference
Predictive analytics and machine learning are not "the same". 

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



