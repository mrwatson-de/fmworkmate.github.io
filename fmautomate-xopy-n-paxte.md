---
title: Xopy 'n' PaXte Code between computers with fmAutoMate
strapline: /ˈksɒp.i n peɪkst/ (verb) — To copy code across the ether, effectively!
parent: fmAutoMate
nav_order: 250
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## Introduction

- Need to transfer some FileMaker code from here to there across the internet quick?
- Wanna copy and paste your FileMaker code between two FileMaker solutions - and it just doesn't work?

## The Problem

- Copy and paste **doesn't work for FileMaker code.** (at least not from a Mac.)
- **However**, copy and paste **does work for text.** (most of the time)

That means, if we can convert our FileMaker code to xml on the clipboard, we are ready to transfer our code across the ether…

## MrWatson's Solutions

Two solutions help bridge the divide:

[fmCheckmate](./fmcheckmate.html) is **quick** (particularly if you use [fmCheckMate's Convert & Transfer Mode](fmcheckmate-modes.html)):

![](/assets/images/fmcheckmate-convert-and-transfer-mode.png)

### Copy Code from here to there with fmCheckMate (Mac to Win)

1. <kbd>⌘</kbd><kbd>C</kbd>
   : **Copy** your code from the FileMaker solution here
2. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd>
   : **Convert** the code here to fmxml on the clipboard with fmCheckMate
3. <kbd>⌃</kbd><kbd>⌥</kbd><kbd>C</kbd>
   : **Convert** back to FileMaker Objects with fmCheckMate there
4. <kbd>⌃</kbd><kbd>V</kbd>
   : **Paste** the code into the FileMaker solution there

### Copy Code from there to here with fmCheckMate (Win to Mac)

1. <kbd>⌃</kbd><kbd>C</kbd>
   : **Copy** your code from the FileMaker solution there
2. <kbd>⌃</kbd><kbd>⌥</kbd><kbd>C</kbd>
   : **Convert** the code here to fmxml on the clipboard with fmCheckMate
3. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd>
   : **Convert** back to FileMaker Objects with fmCheckMate here
4. <kbd>⌘</kbd><kbd>V</kbd>
   : **Paste** the code into the FileMaker solution here

---

[fmAutoMate](./fmautomate.html)'s Xopy + PaXte  is **blitz schnell**:

When the local and remote machines are both Macs, you can use fmAutoMate's Xopy + PaXte to copy code between them:

![](/assets/images/fmautomate-xopy-n-paxte.png)

1. <kbd>⌃</kbd><kbd>⌘</kbd><kbd>C</kbd>
   : **Xopy** the code from the FileMaker solution here
2. <kbd>⌃</kbd><kbd>⌘</kbd><kbd>V</kbd>
   : **PaXte** the code into the FileMaker solution there

Sorted 😎
