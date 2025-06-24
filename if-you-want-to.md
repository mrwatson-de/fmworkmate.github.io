---
title: If you want to
strapline: …
parent: Help
nav_order: 0200
layout: default
---
{: .under-construction }
Page under construction

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## …get an overview of all MrWatson's Tools

…look no further! Here is a schematic diagramme of all my tools and how they relate to each other and to the FileMaker developer environment:

![Overview of MrWatson's Tools](/assets/images/mrwatsons-tools-overview-2025.png)

## …transfer code easily between FileMaker Solution deployments / versions

- You need [fmWorkMate] > [fmCheckMate]

## …catch errors when I paste code into a database

- You need [fmWorkMate] > fmLogAnalyser to be able to read the import.log file and turn it into a todo list
- You need [fmWorkMate] > [fmCheckMate] + the [fmCheckMate-XSLT] Library
  - to check for errors in pasted custom functions or layouts

## …check your layout for errors

- You need [fmWorkMate] > [fmCheckMate] > Layout Analysis

## …move a complicated table between files

Hm … this is a tricky one…

- You need [fmWorkMate] > [fmCheckMate]
- You need the [fmCheckMate-XSLT] Library
  - to undelete fields
- You need [fmWorkMate] > [fmLogAnalyser] - to check for errors when pasting the fields in
- You need [fmWorkMate] > [fmDBAnalyser] - to create compact relationship info
- You need [fmWorkMate] > [fmTextDiff] - to compare the compact relationship info

## …use MrWatson's tools on a Windows PC

You're kind of in luck

- You need the [fmWorkMate] for Windows Runtime

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckMate]: fmcheckmate.html
[fmCheckMate-XSLT]: fmcheckmate-xslt.html
[fmDBAnalyser]: fmdbanalyser.html
[fmLogAnalyser]: fmloganalyser.html
[fmTextDiff]: fmtextdiff.html
[fmWorkMate]: fmworkmate.html
