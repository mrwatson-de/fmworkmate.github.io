---
title: fmTextConverter
strapline: There's no better substitute
parent: Text Tools
nav_order: 5
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

fmTextConverter lets you perform multiple text substitutions on a text. If you are doing a single search and replace [fmCheckMate](fmcheckmate.html) is great but it becomes hard work when you have a whole list of changes that you need to make. That's where fmTextConverter comes in.

fmTextConverter is basically a wrapper for the FileMaker `Substitute` function, and lets you specify a list of search and replace pairs, and then apply them all in one go.

![fmTextConverter screenshot with instructions](/assets/images/fmtextconverter-screenshot-with-instructions.png)

### Converting Text with fmTextConverter

To create a new conversion in fmTextConverter:

- Create a new blank record <kbd>⌘2</kbd>
- Add the list or search terms in the`Search Values` field. <kbd>⌘V</kbd>
- Add the list or replace terms in the `Replace Values` field. <kbd>⌘V</kbd>
- Paste the text you want to convert into the `Text` field. <kbd>⌘V</kbd>
  - Use the `Paste Text` button <kbd>⌘3</kbd> or the menu command `Edit > Paste FileMaker-Clipboard → XML` (<kbd>⌘⌥V</kbd>) to automatically convert FileMaker objects to XML.
- Press the `Convert text now` button <kbd>⌘7</kbd>
  - The converted text will be shown in the `Result` field, and is already on the clipboard.
- Press the <kbd>→ FM</kbd> button to convert the text back to FileMaker objects.

### Tips

- Important! Search is case sensitive.
- Beware substrings - They can cause [unexpected problems](#problem-substrings)
- When working with XML text, you need to consider the encoding for special XML characters - see below.

### Adding and splitting a list of search and replace terms

Have you got your list of search and replace terms as a list of search and replace terms?

No Problem! Just paste the text into the search field, choose the delimiter it uses (click the radio button for tab) and press the `Split Search → Replace` button:

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-1.png)

and fmTextConverter will split the text into pairs of search and replace terms

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-2.png)

### Problem: Substrings

Beware substrings! If one search term is a substring of another you may end up not getting the results you expect, because the first search term will be replaced before the second one is applied. For example, if you have a search term `abc` and a search term `abcd`, then `abc` will be replaced first, and the result will not contain `abcd` anymore.

#### Solution: Sort the lines in decreasing length

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

For example, if you want to replace `mine & yours` with `'mine' and 'yours'` in your code, you will need to encode the special characters in both search and replace terms:

Search term
: `mine &amp; yours`

Replace term
: `&apos;mine&apos; and &apos;yours&apos;`

### Multiple conversions / Killer Keyboard Mode

Once you have set up a conversion in fmTextConverter, if you need to apply the conversion repeatedly to different objects you can use `killer keyboard mode` to repeat the conversion with very few keystrokes:

{% capture killer-keys %}

In FileMaker
: <kbd>⌘X</kbd> to cut the old code out

[In fmWorkMate
: <kbd>⌘6</kbd> to open fmTextConverter]

{: .lowlight}

In fmTextConverter
: <kbd>⌘6</kbd> to convert the code (FM → Convert → FM)
from <kbd>⌘7</kbd> or <kbd>Ctrl+7</kbd> will open the fmTextConverter window.

[In FileMaker (layout objects)
: <kbd>⌘B</kbd>, <kbd>⌘L</kbd> (the browse-mode-layout-mode dance:) to reset the positioning]

[In FileMaker (script workspace)
: <kbd>↑</kbd> to correct the insert point]

In FileMaker
: <kbd>⌘V</kbd> to paste the new code in

{% endcapture %}<section>{{ killer-keys | markdownify }}</section>{: .fullwidth .mrw-killer-bg}