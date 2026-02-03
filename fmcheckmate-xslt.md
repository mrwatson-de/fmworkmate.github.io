---
title: fmCheckMate-XSLT Library
strapline: Transforms your FileMaker work
parent: fmCheckMate
nav_order: 0310
layout: default
github_repo: https://github.com/mrwatson-de/fmCheckMate-XSLT
github_latest: https://github.com/mrwatson-de/fmCheckMate-XSLT/releases/latest
---
[![Get me on Github](/assets/images/get-me-on-github.png){: .w-32}{: .mrw-github-corner}]({{page.github_latest}})

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

The fmCheckMate-XSLT is a library of functions that plug into [fmCheckMate] via the `[T]` Transform button.

## Installation

1. [Download the latest release]({{page.github_latest}}) from GitHub and install it:
  - unpack it
  - rename it to just `fmCheckMate`
  - put the fmCheckMate-XSLT library in your Documents folder, where it lives
    - `~/Documents/fmCheckmate`
  ```sh
  mv ~/Downloads/fmCheckMate-XSLT* ~/Documents/fmCheckMate
  ```
2. In fmCheckMate to open the XSLT Chooser window
   - press <kbd>⌘</kbd><kbd>T</kbd> (T is for **T**ransform), or
   - navigate to the XML Editor (<kbd>⌘</kbd><kbd>3</kbd>) and press the `[T]` button.
3. To load / reload the XSLT library press the `[Reimport]` button or press <kbd>⌘</kbd><kbd>8</kbd>.

## `[T]` is for Transform

Once you have converted your FileMaker things to XML, click the `[T]` button or press <kbd>⌘</kbd><kbd>T</kbd> to open the XSLT Chooser dialog:

![T Button](/assets/images/fmcheckmate-xml-editor-t-button.png)

## The XSLT Chooser Window

If the XSLT files are not yet loaded, click the `[Reimport]` Button or press <kbd>⌘</kbd><kbd>8</kbd> to reimport the files.

The XSLT Chooser has two views

- Guided View
- List View

Press the `[View]` button to switch between the two.

### Guided View

Use the `[View]` button if necessary to change to the Guided View.

In Guided View you are presented with the [three categories of XSLT function](#three-categories-of-xslt-functions)…

![XSLT Chooser Guided View 1](/assets/images/fmcheckmate-xslt-chooser-guided-view-screenshot-1-category.png)

Each entry shows how many xslt transformations it contains. Clicking an entry selects the contents of that entry, and so you work your way down the tree and words of the file name…

    category > input type > output type > First word > Second word > …

Choose input type:

![XSLT Chooser Guided View 2](/assets/images/fmcheckmate-xslt-chooser-guided-view-screenshot-2-input-type.png)

Choose output type:

![XSLT Chooser Guided View 3](/assets/images/fmcheckmate-xslt-chooser-guided-view-screenshot-3-output-type.png)

Where there is only one file left in a category you see the file icon and can choose it, otherwise you continue to distinguish between the names of the different functions.

### List View

Use the `[View]` button if necessary to change to the List View.

![XSLT Chooser List View](/assets/images/fmcheckmate-xslt-chooser-screenshot.png)

## fmCheckMate-XSLT library structure

The fmCheckMate-XSLT library structures its functions by

- [Type of input](#type-of-input)
- [Type of output](#type-of-output)
- [Category](#three-categories-of-xslt-functions), based on how the output type relates to the input type.

### Three Categories of XSLT Functions

fmCheckMate distinguishes three categories of transformation, depending on the input and output type:

An Analysis
: analyses the things and produces a text output (**output type = text**),
  for example the XSLT function to list the names of the copied custom functions is an analysis

A Change
: changes the things without changing the type (**output type = input type**)
  for example the XSLT function to replace a Replace Field Contents Step with a Set Field Loop is a Change

A Transformation
: transforms the things into a different type (**output type ≠ input type**)
  for example the XSLT function to convert layout buttons to script steps is a Transformation

### Type of Input

The XSLT functions of the fmCheckMate-XSLT library are stored in the `xsl`subfolder.

There the functions are grouped into a folder based on the **type of input** that they take:

    fmCheckMate
        xsl
            FMObjectTransfer - the XML format for custom menus
            FMPXMLRESULT - the XML export data format
            FMSaveAsXML - the XML from the Save a Copy as XML step
            fmxmlsnippet - the FileMaker clipboard XML
            FPSL - the XML format of a snapshot file
            xml - any xml
            xsl - an XSLT stylesheet
            _inc - a folder of building blocks include in XSLT functions

### Type of Output

![Analyse Text](assets/images/fmcm-xslt-analyse-text-sm.png){: .w-32}
: Analysis which outputs text

![Analyse Text/Lines](assets/images/fmcm-xslt-analyse-text.lines-listsm.png){: .w-32}
: Analysis which outputs text lines

![Analyse Text/Tab](assets/images/fmcm-xslt-analyse-text.tab-sm.png){: .w-32}
: Analysis which outputs tab delimited text (displayed as an HTML table)

![Analyse Text/HTML](assets/images/fmcm-xslt-analyse-text.html-sm.png){: .w-32}
: Analysis which outputs HTML text

![Statistics](assets/images/fmcm-xslt-analyse-statistik-sm.png){: .w-32}
: Analysis which outputs a text chart

![Analyse Text/SVG](assets/images/fmcm-xslt-analyse-text.svg-sm.png){: .w-32}
: Analysis which outputs a text/svg image

![Analyse Text/Tiny Graph Format](assets/images/fmcm-xslt-analyse-text.tgf-sm.png){: .w-32}
: Analysis which outputs **t**iny **g**raph **f**ormat (displayed in external tool)

![Change](assets/images/fmcm-xslt-change.png){: .w-32}
: Change which outputs the same type of things

![alternative Change](assets/images/fmcm-xslt-change2-sm.png){: .w-32}
: Performs an alternative Change on FileMaker objects

![Folder](assets/images/fmcm-xslt-folder-sm.png){: .w-32}
: ??? To do

![Transform](assets/images/fmcm-xslt-transform-sm.png){: .w-32}
: Transforms the input thing to a different kind of output thing - quite magical 🦄

### The Structure of XSLT Filenames

The filenames of XSLT functions in the fmCheckMate XSLT library are structured like this

    «input-type»_«output-type»_«NameOfTheFunctionInUpperCamelCase».xsl

When the files are imported this is parsed into the three columns

- Input type
- Output type
- Name of the Function

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckMate]: fmcheckmate.html
