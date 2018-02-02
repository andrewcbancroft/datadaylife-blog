---
title: "Fix SSIS Flat File Destination Error: Cannot open the datafile"
excerpt: "Here's how to fix the \"Cannot open the datafile\" error with SSIS Flat File Destinations."
layout: single
toc: true
date: 2018-02-01
categories: [SQL Server]
---

This SSIS package execution error can occur for a few reasons:

* Path to the file does not exist

So for example, if you're writing the file to C:\Some\Folder\somefile.txt, C:\Some\Folder needs to exist **first**.

**Fix**:  Create the folder that the package will write to prior to executing it.  

Alternatively, you can add a File System Task with a `Create Directory` operation prior to the Flat File Destination component.

* The account executing the package does not have permissions

Check to make sure whichever account is executing the package has sufficient file system permissions to write the file to disk.

**Fix**:  Grant the appropriate write permissions to the user account that is executing the package. On a server, this would be the SQL Server Agent account that's executing the package.

* The file you're writing to is being used by another process

If some other process is using the file you're writing to, it will block SSIS' attempt to write to it simultaneously.

**Fix**:  In general, make sure that the file is not in use by some other application or process.  

Be careful copying and pasting SSIS tasks and components inside of a package -- If you *do*, make absolutely sure you've adjusted each configuration appropriately.  I've run into this "file is being used by another process" situation because I copied and pasted an Execute Package task, and forgot to update the config -- attempting ot execute the same package in parrallel can cause issues, apparently!  haha
