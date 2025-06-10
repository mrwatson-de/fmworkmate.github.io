---
title: Recontextualise code with fmAutoMate
strapline: Same fields, different TO
logo: /assets/images/beermats/beermat-rock-n-roll.png
parent: fmAutoMate
nav_order: 5200
layout: default

---
- TOC
{:toc}

{% include page-image.html width="400" %}

# {{page.title}}

{{page.strapline}}

## Problem

You need to change something in some FileMaker code, for example maybe the TO of *every* field in a portal to the new LayoutTable / PTO.


## Solution

For a super-fast fix on a Mac you can use `fmAutoMate > Find & Replace > Find & Replace ALL in XML` to recontextualise code in place

{% capture killer-keys %}

In FileMaker
: <kbd>⌃⌘A</kbd> to search and replace within (the XML of) the selected code.

{% endcapture %}<section>{{ killer-keys | markdownify }}</section>{: .fullwidth .mrw-killer-bg}

## Recontextualise Code Directly on the Clipboard

You can use fmAutomate's Extended Commands to edit the text on the clipboard directly.

{% capture killer-keys %}

In FileMaker
: <kbd>⌃⌘X</kbd> to Xut out the code from FileMaker
: <kbd>⌃⌘K</kbd> to show the fmAutoMate Extended Commands dialog

Extended Command
: <kbd>cba</kbd> for **c**lip**b**oard **a**ll replace

In dialog
: enter the search and replace strings + press <kbd>⏎</kbd> to replace on the clipboard

In FileMaker
: <kbd>⌃⌘V</kbd> to PaXte the changed code back into FileMaker

{% endcapture %}<section>{{ killer-keys | markdownify }}</section>{: .fullwidth .mrw-killer-bg}


