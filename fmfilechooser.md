---
title: fmFileChooser
strapline: A plug-and-play file chooser!
parent: Roadmap
nav_order: 30
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## Problem

Why is choosing and opening a file so hard?

Well, there's a few steps to take.

- filtering or limiting the types files a user can choose.
- getting the path to the chosen file
- discovering what kind of file it is
- handling binary files
- handling text files
  - recognising and handling encoding
  - dealing with BOM characters
  - offering the user a manual encoding override
  - handling EOL characters
  - reading the file in without BOM characters.

## Solution

fmFileChooser is a File-Module you can drop into your solution to easily add file choosing functionality to your FileMaker solution.

### More to come.

Currently in development for [fmThings] and [fmCheckMate].

---

## P.S.

There are also the issues of

- handling display of different files
  - text files
  - image files
  - PDF files
  - XML files
  - JSON files
  - CSV files
  - other structured text files
  - binary files
- round tripping
  - saving files back in the same format you loaded them in
  - same encoding
  - same EOL characters
  - same BOM characters

But that's for another day. :D

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckMate]: fmcheckmate.html
[fmThings]: fmthings.html
