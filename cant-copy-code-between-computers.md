---
title: Can't copy code between computers
strapline: 
parent: Solutions to Daily Problems
nav_order: 2000
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

### Introduction

- Need to transfer some FileMaker code from here to there across the internet quick?
- Wanna copy and paste your FileMaker code between two FileMaker solutions - and it just doesn't work?

### The Problem

- Copy and paste **doesn't work for FileMaker code.** (at least not from a Mac.)
- **However**, copy and paste **does work for text.** (most of the time)

That means, if we can convert our FileMaker code to xml on the clipboard, we are ready to transfer our code across the ether…

### MrWatson's Solutions

Two solutions help bridge the divide:

[fmCheckmate](./fmcheckmate.html) is **quick** (particularly if you use [fmCheckMate's Convert & Transfer Mode](fmcheckmate-modes.html)):

![](/assets/images/fmcheckmate-convert-and-transfer-mode.png)

1. <kbd>⌘</kbd><kbd>C</kbd> - Copy your code from the FileMaker solution here
2. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd> - Convert the code here to fmxml on the clipboard with fmCheckMate
3. <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd> - On the remote computer convert the fmxml from the clipboard with fmCheckMate
4. <kbd>⌘</kbd><kbd>V</kbd> - Paste the code into the FileMaker solution there

---

[fmAutoMate](./fmautomate.html)'s Xopy + PaXte  is **blitz schnell**:

![](/assets/images/fmautomate-xopy-n-paxte.png)

1. <kbd>⌃</kbd><kbd>⌘</kbd><kbd>C</kbd> - Xopy the code from the FileMaker solution here
2. <kbd>⌃</kbd><kbd>⌘</kbd><kbd>V</kbd> - PaXte the code into the FileMaker solution there

Sorted 😎
