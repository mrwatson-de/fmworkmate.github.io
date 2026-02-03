---
title: Transfer code across the ether with fmCheckMate
strapline: Beam me up Scotty!
logo: /assets/images/beermats/beermat-rock-n-roll.png
layout: default
parent: fmCheckMate
nav_order: 100

---
- TOC
{:toc}

{% include page-image.html width="600" %}

# {{page.title}}

{{page.strapline}}

## Problem

Can't copy FileMaker from here to there? From there to here?

This is one of the unusual cases, where Windows tops MacOS and doesn't suffer at all. Mac on the other hand just refuses to beam structured data across the ether…

## Solution

is to convert that code to text/xml…

![fmChekMate](fmcheckmate.png){: .float-front-right .w-48}

Use fmCheckMate to convert the clipboard to/from xml.

1. Install fmWorkMate here
2. Install fmWorkMate there
3. Open fmWorkMate here
4. Open fmWorkMate there
5. Copy code here
6. Convert to XML here with fmCheckMate
7. Convert to FileMaker objects there with fmCheckMate
8. Paste code there

![fmChekMate's Convert and Transfer mode](/assets/images/fmcheckmate-convert-and-transfer-mode.png){: .float-front-right .w-128}

This is where it started, but in the meantime there are better ways to do it …

### Much Better Solutions

![fmChekMate's Convert and Transfer mode](/assets/images/fmcheckmate-convert-and-transfer-mode.png){: .float-front-right .w-128}

If you are patching some code over to a customer's machine and doing a lot of transferring you might want to [put fmCheckmate into `Convert and Transfer` mode](fmcheckmate-modes.html#convert--transfer-mode).

![fmAutomate's Xopy & PaXte](fmautomate-xopy-n-paxte.png){: .float-front-right .w-48}

Alternatively use [fmAutomate's Xopy & PaXte](fmautomate-xopy-n-paxte.html) functions.

### 🎬 Cut! Scrap that!

![MBS-Plugin](mbs-plugin.png){: .float-front-right .w-48}

just use the [MBS Plugin's new automatic clipboard conversion](mbs-convert-clipboard.html). Nice one Christian! :D
