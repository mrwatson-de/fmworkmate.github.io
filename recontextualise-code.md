---
title: Recontextualise Code
strapline: Move code to a new context
logo: /assets/images/beermats/beermat-rock-n-roll.png
parent: Solutions to Daily Problems
nav_order: 200
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}




### Problem

Have you got some code working in one place you want to move to another place?

- maybe from one file to another file
- or move code from one layout to another
- or maybe code from a portal (based on a related table) is needed in the list view (on the PTO).
- or some such thing?

Yes, you can maybe do this with copy and paste, however,

- you need to change the TO of *every* field to the new LayoutTable / PTO
- …*and every calculation* - conditional formatting condition, hide calculation, tip or placeholder calculation also needs to be changed?
- …*and every button script parameter* also may need changing?

(…and if you are recontextualising fields, they might break in the new context before you have time to rename stuff)

That could all be quite a lot of work, surely we can do better…

### MrWatson's Solutions

For **simple recontextualisation** (old TO name -> new TO name)

- On Mac use [fmAutoMate to recontextualise code](recontextualise-code-with-fmautomate.html) directly in the FileMaker GUI (simple and super-fast! 🤩)
- Use [fmCheckMate to rename all the TO references](recontextualise-code-with-fmcheckmate.html) in a single replace action

For **more complex recontextualisation** (multiple old TO names -> new TO names, and/or old field names -> new field names)

- Use [fmTextConverter to create a more complex list of names to change](recontextualise-code-with-fmtextconverter.html) (expert solution 😎)

Alternativaly, on a Mac you can use [fmAutoMate to recontextualise code directly on the clipboard](recontextualise-code-with-fmautomate.html#recontextualise-code-directly-on-the-clipboard) (super-fast but a bit tricksy! 🤩)
