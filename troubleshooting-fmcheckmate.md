---
title: Troubleshooting fmCheckmate
strapline: The Devil is in the Detail
parent: fmCheckmate
nav_order: 9000
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Having trouble getting [fmCheckmate] to work.

## I'm having' search & replace problems

There's a couple of problems you can have when trying to search & replace terms…

### I have an unwanted return character in search & replace terms

We are used to pressing return to make stuff happen, but in fmCheckMate you need to press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>A</kbd> to make the search & replace happen.

### The `[A]` button has disappeared

If you input multiple lines in the replace field
: the button changes to `[M]` which performs a text multiplication with [fmTextMultiplier] when pressed

If you input multiple lines in the find and replace field
: the button changes to `[C]` which performs a text conversion with [fmTextConverter] when pressed

### I want to find and/or replace multiple lines

If you want to find and replace multiline text, enter the multiline search and / or replace terms and press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>A</kbd> to replace all occurrences of the 

## Text is not being found / not converted

Possible causes

- Search is case sensitive -> wrong case
- Are you searching XML text? XML text encoding
- Search term substring problem

### Problem: Substrings

Beware substrings! If your search term is not long enough you might match text you don't mean to match. Make your search term longer to avoid this problem.

If you can't avoid this problem, because your search term is a substring of some other text you can fix the problem using one of these methods:

1. Avoid the substring problem by temporarily changing the longer string, for example, if you want to rename AT in RG, but it is breaking the XML's CDATA keyword by renaming it to CDRGA, you can avoid this by temporarily renaming…
    - replace CDÀTA` with `CDatA`
    - then rename `AT` to `RG` and finally
    - rename `CDatA` back to `CDÀTA`
2. Fix the broken stuff afterwards, for example:
    - replace `AT` with `RG`
    - replace `CDRGA` back to `CDÀTA`

{: .note}

If you find yourself doing this regularly, you may want to create the substitution in [fmTextConverter] to perform the 3 search & replace actions in one go.

### Encoding special XML characters

The following characters are encoded in XML

| Character | XML      |
| :-------: | :------: |
| `&`       | `&amp;`  |
| `<`       | `&lt;`   |
| `>`       | `&gt;`   |
| `"`       | `&quot;` |
| `'`       | `&apos;` |

For example, if you want to replace `mine & yours` with `'mine' and 'yours'` in your code, you will need to encode the special characters in both search & replace terms:

Search term
: `mine &amp; yours`

Replace term
: `&apos;mine&apos; and &apos;yours&apos;`

## Too much text is being found and converted

Possible causes

- Search phrase is not specific or long enough, and XML structure words are being matched

### Solutions

- Make the search phrase more specific, e.g. by adding more text to the search term.
- Add extra search & replace terms to avoid / fix the problem


## The XML is broken

Yes, when working with FileMaker XML code it *is* possible to break the XML.

{: .note }
You can return to a previous version of the XML / navigate the XML history by pressing <kbd>⌃</kbd><kbd>↑</kbd> /<kbd>↓</kbd>.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckmate]: fmCheckmate.html
[fmTextConverter]: fmtextconverter.html
[fmTextMultiplier]: fmtextmultiplier.html
