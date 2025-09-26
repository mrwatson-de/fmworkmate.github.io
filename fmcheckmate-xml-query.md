---
title: fmCheckMate XML-Query
strapline: Query your XML Structure with XPath, XSLT, XQuery
parent: fmCheckMate
nav_order: 300
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Sometimes you just need to quickly dip into the XML structure of your FileMaker file to get some information out of it.

fmCheckmate's XML Query feature not only lets you do just that, but offers 4 different ways to query your XML structure:

1. **XML Structure** - for a quick overview get a dump of the entire XPath structure of your XML
2. **XPath** - pick the cherries out of your XML using XPath (v1.0)
3. **XSLT** - for more flexibility with the XML transformation language
4. **XQuery** - for the most powerful queries use the de facto XML query language XQuery[^1]

[^1]: Note: Advanced XML features, XQuery (and XSLT v2+), require an MBS/Saxon licence, but can be previewed first.

## The XML Query Dialog

To open the XML Query dialog from the fmCheckmate XML Editor…

- select `XML Editor > Show XML-Query` from the menu or press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>X</kbd>

![The XML Query Dialog](/assets/images/fmcheckmate-xml-query-dialog.png)

The Back Button
: Click the `Back` button to close the window, or press <kbd>⌘</kbd><kbd>1</kbd> to go back Home.

The heading
: The heading shows which XML Query technology is currently active. XPath is the default. Click the heading to switch between the Query technologies.

The query input field
: At the top in the middle is the input field for your query.

The output options
: To the right of the input field is the output options / header text. Here you can choose the type of output (XML, Text, in XQuery even JSON) and set additional options depending on the selected XML Query technology, for example you can choose to output unique and/or sorted values.

The Play button
: Click the `Play` button to execute your query.

The Functions button
: Click the `Functions` button to open a list of available functions for the currently selected XML Query technology (under construction).

The Output field
: The large text area at the bottom is the output field where the results of your query are shown.

## XML Structure

To get a quick overview of the XML structure of your FileMaker file

- select `Analyse XML Struture` from the `fmCheckMate`menu or press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>S</kbd>

![XML Structure](/assets/images/fmcheckmate-xml-query-xml-structure.png)

## XPath

In `XPath mode` you can enter any valid XPath v1.0 expression to query the XML structure of your FileMaker file.

![XPath](/assets/images/fmcheckmate-xml-query-xpath.png)

Alternatively you can choose from the value list of xpaths from the structure of your document.

![Choose XPath from the structure](/assets/images/fmcheckmate-xml-query-xpath-value-list.png)

### XPath output options



## XSLT


## XQuery

