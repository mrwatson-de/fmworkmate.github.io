---
title: fmTextDiff
strapline: Makes all the difference.
parent: Text Tools
nav_order: 5
layout: default
---
1. TOC
{:toc}


{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}


One of my favourite tools, fmTextDiff is a simple but powerful tool that 'makes all the difference' when you need to compare two files, texts or even FileMaker code straight up!

## The Problem

Very often we need to know what the differences are between two versions of a database, in order to know what has changed.

When faced with a whole bunch of scripts, pages and pages of script steps, or a long list of fields, the job of finding all the differences can lie somewhere on the scale from daunting to impossible.

Yes, there are analysis tools that can help, but they often only work on the entire-database level and require hours to run.

## The Solution

fmTextDiff works like you work, allowing you to concentrate on one bit at a time.

{:.mrw-green-bg}
If you can copy it from FileMaker, you can diff it with fmTextDiff!

Just

1. copy the thing you want to compare out of the *old* FileMaker version,
   - when copying locally
     : use <kbd>⌘</kbd><kbd>C</kbd>

     with fmAutoMate from a remote Mac
     : use <kbd>⌃</kbd><kbd>⌘</kbd><kbd>C</kbd> to [Xopy the code as XML to the local clipboard](fmautomate.html#copy-the-code-to-the-clipboard),

     from remote mac
     : use <kbd>⌘</kbd><kbd>C</kbd> + fmCheckMate to [transfer code between computers](transfer-code-across-the-ether-with-fmcheckmate.html)

     from remote windows
     : use <kbd>⌃</kbd><kbd>C</kbd> + old fmWorkMate runtime > fmCheckMate 
2. paste it into fmTextDiff
   - open fmTextDiff from fmWorkMate with <kbd>⌘</kbd><kbd>7</kbd>,
   - in fmTextDiff press <kbd>⌘</kbd><kbd>7</kbd> to paste the code into the next free (left) slot,
3. copy the equivalent thing out of the *new* FileMaker version
4. press <kbd>⌘</kbd><kbd>7</kbd> in fmTextDiff again to paste the code into the next free (right) slot
   - fmTextDiff automatically starts diffing the two pieces of code.

Note that as you insert the code, fmTextDiff asks fmCheckMate to convert the code to the best text format for diffing:

Scripts & Steps
: a one-line-per-step representation of the script.

Tables and Fields
: a one-line-per-field representation of the field and calculation.

 Custom Functions
: a one-line-per-function representation of the function.




![fmTextDiff Inputs](/assets/images/fmtextdiff-inputs.png)

## How to

- To compare files,
- To compare texts
- To compare code on the clipboard
