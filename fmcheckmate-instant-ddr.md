---
title: fmCheckMate Instant DDR
strapline: Faster and smarter analysis
parent: fmCheckMate Settings
nav_order: 030
layout: default
---
- TOC
{:toc}

{: .mrw-schwarz-bg}
This page is a 🚧 WORK IN PROGRESS 🚧

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmCheckMate has a great little trick up its sleeve for more powerful instant analyses:

{: .mrw-gold-bg}
fmCheckMate's `iDDR` (instant DDR) feature builds up DDR-like info from your clipboard. 

![iDDR Settings](/assets/images/fmcheckmate-iddr-setting.png)

With iDDR turned on, fmCheckMate remembers the stuff you copy and can use it in later analyses.

The most powerful use case is combining theme information with layout objects in order to discover style names and not just useless UUIDs.

- Turn on iDDR in the fmCheckmate Settings
  - <kbd>⌘9</kbd> <kbd>⌘9</kbd> > `File` 
  - Check the `Auto-Save iDDR files` box
- Save the Theme info in fmCheckMate's iDDR:Copy the theme
  - Open the Theme dialog in FileMaker
  - Select the theme you want to analyse
  - Copy the theme to the clipboard
  - Convert to XML in fmCheckMate
- Now copy the layout bjects you want to analyse
  - Open the layout in FileMaker
  - Select and Copy the objects to the clipboard
  - Convert to XML in fmCheckMate
- Now analyse the objects supported by the iDDR theme information
  - Press `[T]` to choose a transform
  - Search for `Analyse Layout Objects with iDDR Theme Info`
  - Press <kbd>return</kbd> to run the transform

**FIXME** That, at least, is the theory.
