---
title: FileMakerDoc
strapline: A Documentation Tool & Concept for FileMaker
parent: The ones that didn't make it
nav_order: 3
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{: .mrw-blue-bg }

FileMakerDoc is an attempt to do for FileMaker what Javadocs does for Java.

The idea is to use `@tags` in your script comments to document them, and provide an XSLT transformation in fmCheckMate to generate HTML documentation from the @tags.

Whilst the XSLT transformation never made it to production, the project did have some success:

- in [fmSyntaxColorizer] FileMakerDoc Syntax Colorizing still exists. ˚@tags˚ at the start of a comment get a special colour:

  - Image ToDo

- in the Script Workspace certain `@tags` have been implemented within the MBS Plugin, for example:

  - `@param`
  - `@var`
  - `@return`
  - `@returns`

## @tags for Variable Checking

Above all the `@param` and `@var` tags are useful to mark variables as defined, where the MBS Plugin is unable to recognise them. This is not only documentation, but semantic meaning!

- ToDo Image / explanation

## FileMakerDoc: Discontinued or just sleeping?

FileMakerDoc, which for a while even had a website to its name, never quite got off the ground, not least because around the same time that I started to work on FileMakerDoc, Todd Geist brought out [karbon fmdocs](https://github.com/karbonfm/fmdocs) with almost identical aims, and marketed far more enthusiastically.

{: .mrw-gold-bg }
Although FileMakerDoc is sleeping, I still believe in the value of the concept, and I hope one day to return to it, but for now I have put it on the back burner.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmSyntaxColorizer]: fmsyntaxcolorizer.html
