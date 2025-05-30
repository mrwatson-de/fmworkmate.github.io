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

# {{page.title}}

{{page.strapline}}

fmTextConverter lets you perform multiple text substitutions on a text.

fmTextConverter is basically a wrapper for the FileMaker `Substitute` function, and lets you specify a list of search and replace pairs, and then apply them all in one go.

![fmTextConverter screenshot with instructions](/assets/images/fmtextconverter-screenshot-with-instructions.png)

[Indeed, you can also use it to construct a Substitute function by just using the `Convert Text later` button!]

Note: If you only want to perform a single search and replace [fmCheckMate](fmcheckmate.html) may be the better choice of tool.

{: .mrw-gold-bg}

Whilst fmTextConverter - as the name implies - is primarily [for converting text](#converting-text-with-fmtextconverter), it equally excels at [converting FileMaker code](#converting-filemaker-code-with-fmtextconverter) - the FileMaker code is simply converted to FileMaker XML text for the text conversion.

## Converting Text with fmTextConverter

To create a new conversion in fmTextConverter:

{% capture basic_instructions %}

1. Create a new blank record with the `New` button
2. Paste the text you want to convert into the `Text` field.
   - To insert FileMaker code as XML
     - you can use the `Paste Text` button <kbd>⌘3</kbd>
     - or click in the field and use the menu command `Edit > Paste FileMaker-Clipboard → XML` <kbd>⌘⌥V</kbd>
3. Enter the search and replace terms.
   - If you have just a single list of search and replace pairs, you can easily [split the list](#splitting-a-list-of-search-and-replace-terms) into search and replace terms
4. Press the `Convert text now` button
   - **The converted text** will be shown in the `Result` field, and **is already on the clipboard**.
5. If you want to convert the text back to FileMaker objects, press the `→ FM` button.

{% endcapture %}<section>{{ basic_instructions | markdownify }}</section>{: .fullwidth}

or, using the keyboard shortcuts from the `fmTextConverter` app menu:

{% capture basic_keyboard_instructions %}

<kbd>⌘C</kbd>
: Copy code from FileMaker

<kbd>⌘2</kbd>
: New record in fmTextConverter

<kbd>⌘3</kbd>
: Paste code into fmTextConverter (or in the field press <kbd>⌘⌥V</kbd>)

<kbd>⌘4</kbd>
: Paste search terms into `Search Values` field

<kbd>⌘5</kbd>
: Paste replace terms into `replace Values` field

<kbd>⌘7</kbd>
: Convert text in fmTextConverter

<kbd>⌘8</kbd>
: Copy Result XML to FileMaker Clipboard

<kbd>⌘V</kbd>
: Paste converted code back into FileMaker

{% endcapture %}<section>{{ basic_keyboard_instructions | markdownify }}</section>{: .fullwidth}

### Search Tips

- **Search is case sensitive.**
  - Specify both capital and lowercase versions of the search term if you want to replace both!
- **Make your search terms sufficiently specific** - or long - to avoid unintentional matches and replacing unintended text.
- **[Beware substrings](#problem-substrings)**, for example replacing `Document` then `Documents`, which can cause unexpected problems
- **[Consider XML character encoding](#converting-filemaker-code-with-fmtextconverter)** when working with XML text.
- **If the terms are too long** and lines wrap in the field, it can get difficult to see which search term corresponds to which replace term. In this case **use the expand view button** `<` to show larger fields.

| ![Expand View Button](/assets/images/fmtextconverter-screenshot-expand-view.png) | → | ![Expanded View](/assets/images/fmtextconverter-screenshot-expanded-view.png) |

### Splitting a list of search and replace terms

Have you got your list of search and replace terms as a list of search and replace terms?

No Problem! Just 

1. paste the text into the search field,
2. choose the delimiter it uses (or click the radio button for tab delimited columns) and 
3. press the `Split Search → Replace` button:

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-1.png)

and fmTextConverter will split the text vertically into pairs of search and replace terms

![Two columns](/assets/images/fmtextconverter-screenshot-two-columns-2.png)

And if you want you can use the button again, now titled `Merge Search ← Replace`, to merge the two columns back together again:

![Merge two columns](/assets/images/fmtextconverter-screenshot-merge-two-columns.png)

### Problem: Substrings

Beware substrings! If one search term is a substring of another you may end up not getting the results you expect, because the first search term will be replaced before the second one is applied. For example, if you have a search term `abc` and a search term `abcd`, then `abc` will be replaced first, and the result will not contain `abcd` anymore.

#### Solution: Sort the lines in decreasing length

fmTextConverter has a very simple solution to this problem: Just press the Sort button to sort the search terms in descending order of length. This way, the longest search terms will be applied first, and you will not have any problems with substrings.

![Sort Button](/assets/images/fmtextconverter-screenshot-sort-button.png)

Tip: Pressing the Sort button again returns the records to their original sort order.

## Converting FileMaker Code with fmTextConverter

When converting FileMaker Code with fmTextConverter - and thus working with FileMaker XML text - you need to consider a few things

- [Converting the FileMaker clipboard to/from XML format](#fm--convert-text--fm)
- [Encoding special XML characters](#encoding-special-xml-characters)
- [Avoiding breaking the XML](#avoiding-breaking-the-xml)

### FM → Convert Text → FM

FileMaker objects must, of course, be converted to XML text and back so the text conversion can be applied to the XML.

<kbd>⌘C</kbd>
: Copy code from FileMaker

<kbd>⌘⌥V</kbd>
: Paste code into fmTextConverter

…
: Convert text in fmTextConverter

<kbd>⌘6</kbd>
: Converted text back into FileMaker code

<kbd>⌘V</kbd>
: Paste converted code back into FileMaker

{% capture killer_keyboard_mode %}

If the conversion is already defined, use Killer keyboard Mode to repeat the
conversion with minimal keystrokes:

<kbd>⌘C</kbd>
: Copy code from FileMaker

<kbd>⌘6</kbd>
: `FM → Convert Text → FM`

<kbd>⌘V</kbd>
: Paste converted code back into FileMaker

{% endcapture %}<section>{{ killer_keyboard_mode | markdownify }}</section>{: .fullwidth .mrw-killer-bg}

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

### Avoiding breaking the XML

When working with XML text it is possible to break the XML should you accidentally replace text belonging to the XML structure, rather than only the *text content* you want to convert.

This is seldom a problem, because FileMaker just rejects invalid XML text, and you can just correct your search and replace terms accordingly and try again.

There are several precautions you can take:

Tips:

- **Avoid short search terms**, particularly words which are likely to be part of the XML structure, such as `id`, `name`, `type`, `value`, `Field`, `table` etc.
- **When renaming variables**, if you **include the `$`** you can't go wrong.
- If necessary, add extra terms to avoid or to repair any damage.

{: .fixme }

Example AT -> LS

## Reapplying the Current Conversion

{: .fixme}

…

## Managing your Text Conversions

Text Conversions can be named, saved and reused later.

### Saving your Conversions for Reuse later

You can save your conversions in fmTextConverter for later reuse.

To save a conversion…

- give the conversion a meaningful title
- click the pin icon to lock & protect it from accidental deletion.

![Add Title here](/assets/images/fmtextconverter-screenshot-add-title-here.png)

{: .important-icon }

Important! This only saves the conversion within fmTextConverter, but it does not protect your conversions from being lost during an update of fmWorkMate. For that you must [Save your data before updating fmWorkMate!](#save-your-data-before-updating-fmworkmate).

### Applying an existing Text Conversion

Once you have defined a conversion in fmTextConverter, you can reuse it at any time.

This is very useful, because you often want to apply the same conversion to different things in your FileMaker solution - layout objects, scripts, fields, etc.

![List View](/assets/images/fmtextconverter-screenshot-list-view.png)

- Switch to the list view by clicking the `List` button
- Search for or browse to the conversion you need
- Click the `Edit` button to return to the detail view
- Proceed as above.

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

### Protecting your conversions against deletions

To protect your conversions against accidental deletion, click the pin icon to turn it into a locked pin icon.

In List View you can delete unprotected records by clicking the bin icon.

- If there are **any unprotected records** they will be deleted, no questions asked.
- If there are **only protected records** a dialog will appear asking you to confirm the deletion of the selected protected records.

### **Save your data before updating fmWorkMate!**

{: .mrw-warning-bg }

Warning: fmWorkMate has no update process, so you must save your data before overwriting/updating!

To save your data:

- Change to List View
- Find all the records you want to save
- Press the `Export Conversions` button to export the records to the desktop.

To restore your data:

- Change to List View
- Press the `Import Conversions` button to import the records from the desktop.

