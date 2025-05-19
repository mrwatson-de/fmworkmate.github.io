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

[fmCheckMate](fmcheckmate.html) is great for doing a single search and replace, or maybe a few, but it becomes hard work when you have a whole list of changes that you need to make. That's where fmTextConverter comes in.

fmTextConverter is basically a wrapper for the FileMaker `Substitute` function, and lets you specify a list of search and replace pairs, and then apply them all in one go.


### Killer Keyboard Mode

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