---
title: Text Tools
strapline: The power of text…
parent: fmWorkMate
nav_order: 20
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

[![fmWorkMate Toolbox Screenshot](/assets/images/fmworkmate-toolbox-screenshot.png)](https://github.com/mrwatson-de/fmWorkMate){: .float-front-right .w-20pc}

# {{page.title}}

{{page.strapline}}

The text tools are:

- [fmTextConverter] - for converting text values to other text values
- [fmTextDiff] - for comparing two texts
- [fmTextMultiplier] - for multiplying text values
- [fmTextSeries] - for constructing a series of text values

MrWatson's Text tools don't seem much at first,… but once you have realised that FileMaker code
is nothing but XML (so easily converted with [fmCheckMate] or [fmAutoMate]), being able to manipulate xml text smartly suddenly becomes one of the most powerful tools in your tool belt!

## More Text Tool functions

While the fmText* tools form the core elements of this category, there are a few more tools hidden around the place that should be mentioned here:

- [fmCheckMate] has a built in [text result viewer](fmcheckmate-text-result-viewer.html), which has some very handy text functions
  - tabulated text view
    - just add a separator line (a single dash) after the field name line and look at it in the HTML view
  - Text stats 
    - On the final tab you can find an analysis of the text 's EOL characters and utf-8 multibyte characters, word count and more
- [fmSimpleCalculator](fmsimplecalculator) has some useful functions to discover characters utf-8 or utf-16 multibyte values, and more
- The [Text Mate](text-mate.html) text editor, together with a few Unix commands is also very useful combination for text editing.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmAutoMate]: fmautomate.html
[fmCheckMate]: fmcheckmate.html
[fmTextConverter]: fmtextconverter.html
[fmTextDiff]: fmtextdiff.html
[fmTextMultiplier]: fmtextmultiplier.html
[fmTextSeries]: fmtextseries.html
