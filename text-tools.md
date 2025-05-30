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

# {{page.title}}

{{page.strapline}}

MrWatson's Text tools don't seem much at first,… but once you have realised that FileMaker code
is nothing but XML, being able to manipulate text smartly suddenly becomes one of the most 
powerful tools in your tool belt!

    FileMaker -> Clipboard -> Convert to XML -> Text Tools -> Convert to Clipboard --> FileMaker

While [fmTextSeries](fmtextseries.html), [fmTextConverter](fmtextconverter.html), [fmTextMultiplier](fmtextmultiplier.html) and [fmTextDiff](fmtextdiff.html) form the core of the text tools category, there are a few more tools hidden around the place that should be mentioned here:

- fmCheckMate has a built in [text result viewer](fmcheckmate-text-result-viewer.html), which has a few very handy text functions
  - tabulated text view
    - just add a separator line (a single dash) after the field name line and look at it in the HTML view
  - Text stats 
    - On the final tab you can find an analysis of the text 's EOL characters and utf-8 multibyte characters, word count and more
- fmSimpleCalculator has some useful functions to discover characters utf-8 or utf-16 multibyte values, and more
- Text mate text editor, together with a few Unix commands is also very useful combination for text editing. 
