---
title: Troubleshooting fmTextConverter
strapline: The Devil is in the Detail
parent: fmTextConverter
nav_order: 9000
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Having trouble getting [fmTextConverter](fmtextconverter.html) to work.

## I can't input search & replace terms

There's a couple of problems you can have when trying to input your search & replace terms…

### I have a single list of search & replace terms

No Problem! Just paste the text into the search field, choose the delimiter it uses (or click the radio button for tab delimited columns) and press the `Split Search → Replace` button:

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-1.png)

and fmTextConverter will split the text vertically into pairs of search & replace terms

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-2.png)

And if you want you can use the button again, now titled `Merge Search ← Replace`, to merge the two columns back together again:

![Merge two columns](/assets/images/fmtextconverter-screenshot-merge-two-columns.png)

### Search & replace terms too long / wrapping

If the terms are too long and the lines wrap in the field, it can get difficult to see which search term corresponds to which replace term.

In this case use the expand view button `[<]` / `[>]` to show / hide wider fields:

| Narrow view | `[<]` / `[>]` | Wide view |
| ---- | :-: | --- |
| ![Expand View Button](/assets/images/fmtextconverter-screenshot-expand-view.png) | ↔︎ | ![Expanded View](/assets/images/fmtextconverter-screenshot-expanded-view.png) |

## Text is not being found / not converted

Possible causes

- Search is case sensitive -> wrong case
- Are you searching XML text? XML text encoding
- Search term substring problem

### Problem: Substrings

Beware substrings! If one search term is a substring of another you may end up not getting the results you expect, because the first search term will be replaced before the second one is applied. For example, if you have a search term `abc` and a search term `abcd`, then `abc` will be replaced first, and the result will not contain `abcd` anymore.

#### Solution: Sort lines in decreasing length

fmTextConverter has a very simple solution to this problem: Just press the Sort button to sort the search terms in descending order of length. This way, the longest search terms will be applied first, and you will not have any problems with substrings.

![Sort Button](/assets/images/fmtextconverter-screenshot-sort-button.png)

Tip: Pressing the Sort button again returns the records to their original sort order.

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

ToDo - Example of `AT -> RG`.


