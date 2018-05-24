---
title: To Dimension or Not to Dimension? How to Know When a New Dimension is Required...
excerpt: "It's not always clear how to tell when you should create a new dimension. Here, I explore some clues that might guide you on whether or not you should group columns together, or split them apart into separate dimensions..."
layout: work-in-progress
toc: true
categories: [Data Modeling]
---

So you're building a dimensional model and you're asking he question, "Should I group these columns together, or should I split them into separate dimensions?"

It's not always clear, and when most examples that you run across on the internet are dealing with "obvious" dimensions like Product or Date or Employee, it's hard when you run into ambiguous real-world situations.

Here, I offer a few angles from which you can approach your decision to "Dimension" (or not).

## Ask: What are the organizational units that your users refer to?

Listen to users of your to-be dimensional model.  How do they talk about the stuff they want to analyze?  What terms do they use to delineate how they want to describe their metrics?

Often, the high-level nouns they use are clues as to what could be translated to a dimension table in your dimensional model.

When in doubt, ask the folks who will use the model. Dimensional modeling is highly collaborative by nature, so utilize your business partners when you're unsure of how to organize their data.

## Ask: If I were to create a dimension, how many columns would it have?

## Ask: What attributes change together?

## Ask the extreme:  What if every column was its own dimension?  

## Ask the other extreme: What if we only had one huge dimension?

## Ask: What pieces or chunks of descriptive context will be reused without the need for other chunks of descriptive context?

## Ask: Where will users of your dimensional model go to look for descriptive attributes?

## Think in terms of factoring things out (like in a math problem)

## Think in terms of decomposition

