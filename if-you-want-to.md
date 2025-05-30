---
title: If you want to
strapline: …
parent: Help
nav_order: 1000
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

- You need [fmWorkMate][fmWorkMate] > fmCheckMate

## …catch errors when I paste code into a database

- You need [fmWorkMate][fmWorkMate] > fmLogAnalyser to be able to read the import.log file and turn it into a todo list
- You need [fmWorkMate][fmWorkMate] > fmCheckMate + the fmCheckMate-XSLT Library
  - to check for errors in pasted custom functions or layouts

## …check your layout for errors

- You need [fmWorkMate][fmWorkMate] > fmCheckmate > Layout Analysis

## …move a complicated table between files

Hm … this is a tricky one…

- You need [fmWorkMate][fmWorkMate] > fmCheckMate
- You need the fmCheckMate-XSLT Library
  - to undelete fields
- You need [fmWorkMate][fmWorkMate] > fmLogAnalyser - to check for errors when pasting the fields in
- You need [fmWorkMate][fmWorkMate] > fmDBAnalyser - to create compact relationship info
- You need [fmWorkMate][fmWorkMate] > fmTextDiff - to compare the compact relationship info


## …use MrWatson's tools on a Windows PC

You're kind of in luck

- You need the [fmWorkMate][fmWorkMate] for Windows Runtime
