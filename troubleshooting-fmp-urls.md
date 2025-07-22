---
title: Troubleshooting fmp URLs
strapline: fmp urls can be a bit tricky
parent: fmIDE
nav_order: 9000
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Are you having trouble getting your fmp urls to work?

There are several things that can go wrong with fmp urls - check out the list below.

Alternatively, maybe your fmp url is reaching your FileMaker, but your [fmIDE deep link] parameters are giving you trouble?

# Troubleshooting fmp urls

## The fmp url is not being linked

Many web sites simply do not recognise the fmp:// protocol and leave the url as plain text.

- Just copy and paste the url into your browser address field and press <kbd>⏎</kbd>
- try adding a prefix http:// to the front of the fmp url

## The fmp url is being mangled at source

Many web sites, including the FileMaker Community website, do not support the fmp:// protocol or recognise it as a valid link.

### The fmp:// part of the url is not part of the link

Some web and email systems automatically recognise urls in text, and turn them into links. Often the fmp:// part is **not** recognised as being part of the link and the link starts from the server part of the url.

I am developing a chrome extension that corrects this on the FileMaker Community web pages.

{: .watch-this-space}

Watch this space for more.

### The fmp url is prefixed with http://

This often happens when you enter an fmp url into a system that is expecting 'normal' urls. Just 

## The fmp url is opening in the browser

This is normal, the browser acts as a mediator or url protocols.

**If the start of the url is not correct**, for example `http://fmp//…` or `https://fmp21://…` or similar - simply click in the address field and correct it to `fmp://…` or with a version number `fmp21://…` and press <kbd>⏎</kbd>

## Do I want to open the fmp url? Is it safe?

When the browser asks if you want to open an fmp url in FileMaker, this is normal.

If you trust the fmp url source just say Yes.

## My fmp url is targeting the wrong FileMaker

Tricky.

fmp urls (usually) open in the newest version of FileMaker that has been installed on your machine.

If you want to **open an fmp url in a specific version of FileMaker** use the specific fmp protocoll for that version, for example, if you wish to target FileMaker 21 change the fmp url from `fmp://` to `fmp21://…`

If you have multiple instances of FileMaker on your computer, **you want the fmp url to open in a specific instance** but it is opening in the wrong instance, sadly there is no (known) way to control this, so here you have two simple solutions:

1. go with the flow and just use the instance that receives the fmpurls to do your coding in! 😎
2. delete that instance of FileMaker until your desired instance is correctly targeted. 🤠

### I have a single list of search & replace terms

No Problem! Just paste the text into the search field, choose the delimiter it uses (or click the radio button for tab delimited columns) and press the `Split Search → Replace` button:

![Two columns](/assets/images/fmIDE-screenshot-two-columns-1.png)

and fmIDE will split the text vertically into pairs of search & replace terms

![Two columns](/assets/images/fmIDE-screenshot-two-columns-2.png)

And if you want you can use the button again, now titled `Merge Search ← Replace`, to merge the two columns back together again:

![Merge two columns](/assets/images/fmIDE-screenshot-merge-two-columns.png)

### Search & replace terms too long / wrapping

If the terms are too long and the lines wrap in the field, it can get difficult to see which search term corresponds to which replace term.

In this case use the expand view button `[<]` / `[>]` to show / hide wider fields:

| Narrow view | `[<]` / `[>]` | Wide view |
| ---- | :-: | --- |
| ![Expand View Button](/assets/images/fmIDE-screenshot-expand-view.png) | ↔︎ | ![Expanded View](/assets/images/fmIDE-screenshot-expanded-view.png) |

## Text is not being found / not converted

Possible causes

- Search is case sensitive -> wrong case
- Are you searching XML text? XML text encoding
- Search term substring problem

### Problem: Substrings

Beware substrings! If one search term is a substring of another you may end up not getting the results you expect, because the first search term will be replaced before the second one is applied. For example, if you have a search term `abc` and a search term `abcd`, then `abc` will be replaced first, and the result will not contain `abcd` anymore.

#### Solution: Sort lines in decreasing length

fmIDE has a very simple solution to this problem: Just press the Sort button to sort the search terms in descending order of length. This way, the longest search terms will be applied first, and you will not have any problems with substrings.

![Sort Button](/assets/images/fmIDE-screenshot-sort-button.png)

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

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmIDE]: fmIDE.html
