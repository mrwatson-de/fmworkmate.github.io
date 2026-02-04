---
title: fmCheckMate
strapline: Transforms your FileMaker work
parent: Developer Tools
nav_order: 20
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmCheckMate is part of the [fmWorkMate] toolbox and is installed when you [install fmWorkMate].

## Introduction

fmCheckMate converts your FileMaker objects to/from XML and lets you transfer, analyse, change, transform, edit or find and replace your code.

![fmCheckMate Overview](/assets/images/fmcheckmate-overview.png)

fmCheckMate is the door between your FileMaker code and the xml representation you can edit, analyse or generate. It is a smart little tool, which packs more punch than you at first can imagine.

Not only does it convert your FileMaker code from the clipboard to an XML that you can then edit, change and convert back, but it also changes the contents of the clipboard between FileMaker Objects and text.

This means it is a great tool for [transferring code to/from another computer](transfer-code-across-the-ether-with-fmcheckmate.html).





## Finding & Replacing Text

fmCheckMate is great for finding and replacing text in your FileMaker code, for example [renaming variables in scripts](rename-variables-with-fmcheckmate.html) is really easy.

And if you are moving fields between layouts, or moving scripts between files you can [recontextualise your code with fmCheckMate](recontextualise-code-with-fmcheckmate.html) just by replacing one or a few TO names.

## fmCheckMate Modes

Depending on what you are doing with fmCheckMate, you may want to [select a different mode](fmcheckmate-modes.html), for example `Convert Mode` if you are transferring code between computers and deployments, or `Analysis Mode`if you are [checking layouts for errors](layout-analysis-with-fmcheckmate).

## Extending fmCheckmate with fmCheckMate-XSLT Library

If you want more power at your fingertips, then install the [fmCheckMate XSLT] Library to add hundreds of functions to fmCheckMate.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckMate XSLT]: fmcheckmate-xslt.html
[fmWorkMate]: fmworkmate.html
[install fmWorkMate]: install-fmworkmate.html
