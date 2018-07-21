---
title: Piecing Together the Components of the Hadoop Ecosystem
excerpt: "The list of software components and in the Hadoop ecosystem may be long, but each component exists for a purpose. Discover more about the kind of problem each component solves."
layout: work-in-progress
toc: true
categories: [Big Data, Hadoop]
---

While it's true that originally, "Hadoop" referred primarily to a distributed file system (HDFS), and a programming model for processing data (MapReduce), years of adoption and use have led to an outpouring of community contributions in the form of (mostly) open source projects and frameworks.

Today, "Hadoop" is best thought of as a *composition* of the now *three* core components (HDFS, a newly-introduced resource negotiator called YARN, and MapReduce), and a selection of the various pieces of software and frameworks that have been designed to do what such components are *supposed* to do: To provide developers with a higher-level way to interact with some of the lower-level components... to ease tedious tasks... to provide new, more efficient processing mechanisms over some of the core technologies... to extend the functionality of the base components, etc.

When I approach ecosystems like Hadoop, I try to assume that if a component exists, it exists to solve a particular kind of problem. In other words, it wasn't created randomly or flippantly... someone (or someone**s**) noticed a pain point or a way to improve [something] about the way we could use Hadoop.  He or she imagined a way to make it better, and developed the component to eliminate the pain or make the improvement a reality.

Therefore, it seems reasonable to start piecing things together by asking questions around the particular problems as they arise organically.  Something like this...

# Q: What do you do when a file you have exceeds the storage capacity of your local disk?
One option might be to buy a bigger disk and put it in your computer, true? But as data keeps growing in size, you'll run into a bottleneck where the reasonable capacity for a single disk doesn't keep pace with the volume of data you're storing.

An alternative option might be to buy *more* disks, and split up files into chunks.  The whole file might not fit together on a single disk, but if you split it into smaller chunks and spread them across the disks, you could make it work.

This leads to a sub-question:

## What if one of the disks that a piece of your file is stored on dies?
Nothing lasts forever, so how do you protect against data loss if one of the storage devices fails?

# A: Hadoop Distributed File System (HDFS)

# Q: If you split up a file, how do you piece it back together or work with it as a whole entity?
Presumably you'll want to get the file back into its original form eventually... or at the very least, come up with a way to process it fully as an entire entity, even if it's divided up across storage devices.

# A: MapReduce

