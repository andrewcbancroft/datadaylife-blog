---
title: Predictive Analytics vs Machine Learning - What's the Difference?
excerpt: "Are predictive analytics and machine learning the same thing? If they're not, what's the difference?"
layout: work-in-progress
toc: true
---

There's a strong temptation to equate "predictive analytics" and "machine learning". It's not uncommon to throw the terms around interchangeably, which signals that the two are strongly related.

But is there a *difference* that sometimes gets lost when we substitute one term for the other? If there *is* a difference, is it important to distinguish? Is it dangerous or misleading to use the terms as synonyms?

## Questions -> Data -> Analysis -> Answers
This flow is what it's all about, isn't it?  At the end of the day, you want *answers* so that you can take informed action.

But before you can get **answers**, you need to do a certain kind of **analysis**.

But before you do *analysis*, you need **data** to perform the analysis on.

But before you bother with *data*, you typically have **questions** in mind.  

You're curious about the world, your industry, your process. You make observations and you wonder if doing [something] will impact or *change* [something else] that would lead to [some goal]. 

In order to satisfy your curiosity, you collect [data](https://www.dataday.life/what-is-data-like-im-five/) in the form of [quantitative](https://www.dataday.life/what-is-data-like-im-five/#quantitative-numerical) and [qualitative](https://www.dataday.life/what-is-data-like-im-five/#qualitative-categorical) measurements. 

The data fuels the possibility for analysis, so that hopefully, you walk away with a more complete picture than you had before (ie, you have answers).

## Kinds of Data Analysis
I stumbled upon an article in Science Magazine from March 2015 titled, "[What is the Question?](https://www.d.umn.edu/~kgilbert/ened5560-1/The%20Research%20Question-2015-Leek-1314-5.pdf)". It's a short but insightful article that succinctly summarizes the kinds of analysis that can be done on data.  I love the flow chart that they include, wherein the authors guide you through figuring out what kind of analysis you're doing based on what you do with the data.

### "Did you summarize the data?"
"Did you summarize the data?", they ask?  If not, then **you didn't do data analysis**. 

BUT, if you *did* summarize the data, then...

### "Did you report the summaries *without interpretation*?"
If you just gave 'em the numbers and stopped there, you did **descriptive analysis**.  

BUT if you went further and *did* interpret the results of those summaries, then...

### "Did you quanitify whether your discoveries are likely to hold in a *new sample*?"
Assuming you collected data for a sample (a subset of a population), did you compute anything that would give you any insight into whether or not your discoveries about the data are likely to remain true if you went out and randomly sampled again... and again... and perhaps again?  If you *didn't*, meaning you were satisfied with making interpretations only about your single sample, you did **exploratory analysis**.

BUT, if you *did* calculate some statistics that would allow you to go beyond making interpretations about the data set you have in hand, then...

### "Are you trying to figure out how changing the average of one measurement affects another?"
In other words, are you looking for some kind of cause-effect relationship?

If you're satisfied with making predictions in general, without needing to know the underlying *cause* of the relationships found in your analysis, then we're finally at the stage where we can ask one more question:

"**Are you trying to predict measurement(s) for the whole population, or for specific individuals within a population?**"
If you're making measurement predictions for an entire population, you're doing **inferential data analysis**.  That's what [inferential statistics](https://en.wikipedia.org/wiki/Statistical_inference) is all about -- reasoning from samples to populations.

If you're making measurement predictions for specific *individuals*, you're doing **predictive analysis**.

Now then, if you *did* want to go beyond general predictions and dig down into the level of causation, then...

### "Is the effect you are looking for an average effect or a deterministic effect?"
In other words, when you *change* one measurement, does it "always and exclusively lead to a specific, deterministic behavior in another?"  If so, then you're doing **mechanistic data analysis**.

If you're trying to find out what happens to a measurement *on average* when another measurement changes, then you're doing **causal analysis**

## Summarizing the Kinds of Data Analysis
