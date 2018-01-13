---
title: What Kinds of Data Analysis Are There?
excerpt: "How can we categorize the data analyses we do? How are they related, and does one kind of analysis set you up for another?  Let's explore..."
layout: single
toc: true
categories: [General Data Concepts]
---

I stumbled upon an article in Science Magazine from March 2015 titled, "[What is the Question?](https://www.d.umn.edu/~kgilbert/ened5560-1/The%20Research%20Question-2015-Leek-1314-5.pdf)". It's a short but insightful article that succinctly summarizes the kinds of analysis that can be done on data.  My takeaways include the following:

## How many kinds of data analysis are there?
There are at least six ways to categorize a particular kind of analysis that you can do on data:

1. Descriptive Analysis
2. Exploratory Analysis
3. Inferential Analysis
4. Predictive Analysis
5. Causal Analysis
6. Mechanistic Analysis

![Kinds of Data Analysis]({{ "/assets/data-analysis-kinds.png" | relative_url }})

## How do I know what kind of analysis I've done?
The authors of the referenced article asked the following questions to determine 1) if you've done data analysis at all, and 2) if you have, what kind:

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
If you're making measurement predictions for an entire population, you're doing **inferential data analysis**.  That's what [inferential statistics](https://en.wikipedia.org/wiki/Statistical_inference) is all about -- making estimations about populations based on samples.

If you're making measurement predictions for specific "units" / *individuals*, you're doing **predictive analysis**.

Now then, if you *did* want to go beyond general predictions and dig down into the level of causation, then...

### "Is the effect you are looking for an average effect or a deterministic effect?"
In other words, when you *change* one measurement, does it "always and exclusively lead to a specific, deterministic behavior in another?"  If so, then you're doing **mechanistic data analysis**.

If you're trying to find out what happens to a measurement *on average* when another measurement changes, then you're doing **causal analysis**

## Summarizing the Kinds of Data Analysis
![Kinds of Data Analysis]({{ "/assets/data-analysis-summary.png" | relative_url }})
