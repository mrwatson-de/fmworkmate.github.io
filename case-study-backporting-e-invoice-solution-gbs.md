---
title: Backporting an e-Invoice Solution for GBS GmbH
strapline: Using MrWatson's tools and above all the power of fmIDE
parent: Case Studies
nav_order: 0100
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## The Setting

The technical specification EN16931 has long prepared the path for electonic invoicing in the EU.At first there was a slow uptake from the commercial sector, but towards the end of 2024 in Germany at last the penny dropped…

{: .mrw-orange-bg}
electronic invoicing is *really* coming to Germany

…and quite imminently!

Moreover, the task ahead had just exploded, morphing 

- from the (relatively) simple task of ***receiving* an electonic invoice**
- to the much more complicated task of ***generating* and sending a *valid* electonic invoice**.

## An e-Invoicing Solution

At [Günther Business Solutions GmbH](https://guenther-bs.de/) we scrambled to master the situation - and managed to create a great solution in a couple of very intensive months' consultation and programming. The solution we developed for the [advanter ERP system](https://guenther-bs.de/advanter/) was a two file module: one file for the code and one for the customer's data.

## The Problem

Whilst our prefered delivery method would have been to update all our customers to this new version of the software, there was a problem:

{: .mrw-red-bg}
A handful of customers - about 15 - were stranded in old legacy versions of the software, requiring GBS to [backport](glossary.html#backport) this new functionality into their old systems. 😕


## The Headaches of Backporting Code

As you may know, backporting code into old databases is always a real headache. Databases evolve over time, and it is only natural that things get improved, renamed, extended, restructured. Importing or copy-pasting code between different versions of a database always leads to broken code, and we needed to minimise / eradicate this risk.

Whilst the files were designed to be modular, there was a still a rather large overhead of programming that was needed in the legacy systems to integrate these modules into the legacy framework.

The to do list included, amongst many other things

- **ensuring a clean programming environment**
- **deploying the two new files** to the customers server
- **integrating the two new files** into advanter's standard processes, inc.
  - file authorisation, account & window management, solution startup & shutdown, etc.
- **adding or updating code** to support the new e-Invoice process:
  - custom functions, fields, value lists, layouts, scripts, …
  - settings fields for the e-Invoice process
  - new, normalised line item table to pre-process the data
  - modifying the invoice print script to construct the electronic invoice data as json and interact with the new e-Invoice module


In other words, 

- a lot of manual changes
- in a lot of different systems

We needed to get efficient!

## MrWatson's Tools to the rescue!

MrWatson's tools proved to be most useful in many aspects of this process!

Here is a list of the tools we used, and how they helped.

- MrWatson's [fmWorkMate](fmworkmate.html) toolbox, with all its magic…
- [fmLaunchPad](fmlaunchpad.html)
  - to speed up te database launch process
  - and to make it easier for fmWorkMate to run in a separate FileMaker instance

- Setup tools
  - [fmSetupAssistant](fmsetupassistant.html)
    - to make sure that the FileMaker programming environment on the customers computer was setup correctly
  - [fmKillDefaultFields](fmkilldefaultfields.html)
    - to make sure that the customer's database was clean of default fields
  - [fmSyntaxColorizer](fmsyntaxcolorizer.html)
    - to make sure that errors in scripts were immediately visible

- [fmCheckmate](fmcheckmate.html)
  - to transfer code from our master database to the customer's deployment
- [fmAutoMate](fmautomate.html)
  - to transfer code even quicker using [Xopy 'n' PaXte](xopy-n-paxte.html) 

- [fmLogAnalyzer](fmloganalyzer.html) and the BugOff! Alarm
  - to catch pasting errors as we made them
  - and to turn the errors in a still-to-do list
- [fmCheckMate-XSLT](fmcheckmate-xslt.html) library
  - primarily for layout analysis to check no pasting errors crept into customers' layouts.
- [fmDBAnalyzer](fmdbanalyzer.html)
  - for the specific task of checking the new TOs in the relationship graph.
- [fmTextDiff](fmtextdiff.html)
  - to check how the customer's code and our code differed

The tool, however, which really shone in this process was[fmIDE](fmide.html)

## A To-Do List Solution: Slack Canvas

For the ToDo list we had chosen to use the [Slack Canvas](https://slack.com/intl/en-gb/features/canvas) functionality just released in our team software of choice, [Slack](https://slack.com/).

Thanks to the brand spanking new [Slack Canvas](https://slack.com/intl/en-gb/features/canvas) functionality in our team software of choice, [Slack](https://slack.com/), it was relatively easy to build a comprehensive - but collapsible - to do list, that worked for everyone.


- [Slack Canvas](https://slack.com/intl/en-gb/features/canvas) to build a comprehensive & collapsible to do list

