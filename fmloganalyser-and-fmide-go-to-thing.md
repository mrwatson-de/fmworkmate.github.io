---
title: fmLogAnalyser and fmIDE Go to Thing
strapline: Show me that Broken Thing **NOW**
parent: fmLogAnalyser
nav_order: 4
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmLogAnalyser works together with fmIDE to get to the bugs in the FileMaker IDE with just a few clicks … which is absolutely awesome…

{% capture awesome %}

{:.text-xl .emoji-icon .clear .float-front-right .mt--8}
😎

Getting **information about errors** from fmLogAnalyser is **cool**.

{:.text-xl .emoji-icon .clear .float-front-right .mt--8}
🤩

Receiving a **warning about errors** from the fmLogAnalyser BugOff! Alarm is **amazing**

{:.text-xl .emoji-icon .clear .float-front-right .mt--8}
🤯

But being able to **jump exactly to the error** in your FileMaker solution is **absolutely awesome**.

{% endcapture %}<section class="fullwidth mrw-crescendo3-bg">{{ awesome | markdownify }}</section>

## So, how do you do it?

Prepare your files for deep linking with fmIDE

- Follow the [fmIDE installation instructions](fmide.html#basic-installation) to install the fmIDE module into your solution files, grant developers fmpurl access and setup the fmIDE keyboard buffer key.

All you have to do is

1. Open [fmLogAnalyser] in your development FileMaker Pro
2. Navigate to the log entry showing the error
3. Click the fmIDE icon button, bottom left, or just press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>M</kbd> to jump to the error
   - and, should you need to navigate inside a dialog to the thing, use your fmIDE keyboard buffer key, <kbd>F12</kbd>, to retype the name of the thing.

{: .fullwidth}

![fmIDE button in fmLogAnalyser](/assets/images/fmloganalyser-fmide-button-screenshot.png)

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmLogAnalyser]: fmloganalyser.html
