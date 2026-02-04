---
title: fmLogAnalyser
strapline: PROVES you are right!
parent: Developer Tools
nav_order: 30
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmLogAnalyser is part of the [fmWorkMate] toolbox and is installed when you [install fmWorkMate].

When you paste code into a FileMaker solution (or import them) things can easily break.

Fortunately, when this happens FileMaker ([*mostly*](#what-filemaker-doesnt-log)) creates log entries (in the `import.log` file) to help you find out what went wrong.

## The import.log file

The `import.log` file is created in the same folder next to your FileMaker file, or, for hosted files, in your `Documents` folder.

Whilst it does contain the info you need, it is not very user friendly to read.

fmLogAnalyser to the rescue!

![fmLogAnalyser Screenshot of the Log Analysis](/assets/images/fmloganalyser-screenshot.png)

## fmLogAnalyser - a to do list of errors

FIXME - more to come here

## What FileMaker *doesn't* log

- FileMaker does not log anything from the Layout Workspace.
  - Shame on Claris, because this is really the place you need it the most!
  - MrWatson to the rescue with [Layout Analysis with fmCheckMate]!
- FileMaker does not log custom function paste errors.
  - MrWatson to the rescue with [Custom Function Analysis with fmCheckMate]!

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmWorkMate]: fmworkmate.html
[install fmWorkMate]: install-fmworkmate.html
[Layout Analysis with fmCheckMate]: layout-analysis-with-fmcheckmate.html
