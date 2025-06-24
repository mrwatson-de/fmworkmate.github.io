---
title: Did That Just Break?
strapline: When something breaks in a forest, does it make a noise?
parent: Solutions to Daily Problems
nav_order: 0310
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

And when something breaks in a FileMaker database, does it log an error?

When moving code around, patching files, or generally copy + pasting stuff from A to B, it's quite easy to break things. 

FileMaker tries to help in the form of the import.log which gets written to every time you paste something in, **but…**

## The Problems

1. The import.log is hard to read
2. Some problems are not logged as errors
3. Errors from cancelled imports are hard to recognise
4. Finding the error in the log is one thing, finding the original error is another
5. Custom functions errors are not logged
6. In Layout Mode there is *no logging at all*

## MrWatson's Solutions

MrWatson has a solution for everything

### For Mastering the import.log

First and foremost you need [fmLogAnalyser](./fmloganalyser.html) to help you read the import.log, and the  [BugOff! Alarm](./fmloganalyser-and-the-bugoff-alarm.html) to tell you when you've broken something.

This solves problems 1-3. Errors and warnings (e.g. thing 'x' imported as thing 'x 2') are highlighted and a big green OK button tells you your import was successful.

For problem 4, you need to add [fmIDE](./fmide.html) to your solution. Then it needs approximately a single click to get to the error in your solution
The tonic you need is

Problem 5 and 6, errors in Custom Functions and Layouts, have to be solved differently, since they are not logged. For this you need

- [fmCheckMate](./fmcheckmate.html) (part of [fmWorkMate](./fmworkmate.html))
- [fmCheckMate XSLT-Library](./fmcheckmate-xslt-library.html)!
- and, of course, [the MBS Plugin](./mbs-plugin.html)

### For Custom Functions

…after you paste them in, but *before* you close the Custom Functions dialog,…

- Copy the Custom Functions back to the clipboard
- With fmCheckMate convert them to XML
- Click `[T]` (or press`⌘T`) to choose an XSLT transformation
- Select the analysis function "List functions that seem to be commented out"
- You get a list of suspect CFs

If the list is empty, you can go back and save the custom functions, and if not you can break off, fix the problems and repeat.

### For Layouts

With fmCheckMate and the fmCheckMate XSLT Library you can [perform an instant analysis on any layout](layout-analysis-with-fmcheckmate.html) in your solution.

