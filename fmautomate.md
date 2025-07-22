---
title: fmAutoMate
strapline: Towards a FileMaker IDE
parent: Integration Tools
nav_order: 100
layout: default
tool_name: fmAutoMate
github_repo: https://github.com/mrwatson-de/fmAutoMate
github_latest: https://github.com/mrwatson-de/fmAutoMate/releases/latest
---
[![Get me on Github](/assets/images/get-me-on-github.png){: .mrw-github-corner}]({{page.github_latest}})

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

A tool for FileMaker developers which extends and automates your script workspace and FileMaker environment to provide you with some awesome functions to boost developer productivity (including, in some cases, making the impossible possible 😜).


![fmAutoMate start layout](/assets/images/fmautomate-screenshot.png)

fmAutoMate comprises

1. the main [install fmAutoMate](#install-fmautomate) function, which 
   - installs the [fmAutoMate Context Menus]
     - extends the `Script Workspace` with a [context menu](#an-extension-of-mbs-context-menus) full of all kinds of useful and powerful functions
     - provides a [context menu in layout mode](fmautomate-context-menus.html#fmautomate-layout-workspace-context-menu)
     - provides a [context menu in browse mode](fmautomate-context-menus.html#fmautomate-browse-mode-context-menu)
   - provides keyboard shortcuts ('`HotKeys`') to bring these functions to your fingertips
   - extends the entire FileMaker GUI by introducing [Extended HotKey functions](#fmautomate-extended-hotkeys) <kbd>⌃</kbd><kbd>⌘</kbd><kbd>K</kbd>)
2. the [fmAM Script Module](#fmautomate-fmam-script-module)
   - which adds even more functions to the context menus
3. [fmAutomate Services](#fmautomate-services)
   - which provide (text formatting) functionality in the Mac OS services context menu in text fields throughout your system.

## Install fmAutoMate

![fmAutoMate Install Button](/assets/images/fmautomate-button.png){: .float-front-right}

When you open fmAutoMate in FileMaker Pro and press the `fmAutoMate` button, the following goodies are installed into your FileMaker GUI:

- [fmAutoMate Script Workspace Context Menu](fmautomate-context-menus.html#fmautomate-script-workspace-context-menu) <kbd><samp>Right-click</samp></kbd>
- [fmAutoMate Layout Workspace Context Menu](fmautomate-context-menus.html#fmautomate-layout-workspace-context-menu) <kbd><samp>Right-click</samp></kbd>
- [fmAutoMate Browse Mode Context Menu](fmautomate-context-menus.html#fmautomate-browse-mode-context-menu) <kbd><samp>Right-click</samp></kbd>
- [fmAutoMate Extended HotKeys](fmautomate-extended-hotkeys.html) Dialog (<kbd>⌃</kbd><kbd>⌘</kbd><kbd>K</kbd>) **available everywhere** in the FM GUI

## fmAutomate Extended HotKeys

[fmAutomate Extended HotKeys](fmautomate-extended-hotkeys.html) can be opened by pressing <kbd>⌃</kbd><kbd>⌘</kbd><kbd>K</kbd>

See the [fmAutomate Extended HotKeys](fmautomate-extended-hotkeys.html) page for details.

## fmAutoMate fmAM Script Module

The `fmAM Script Module` is a group of scripts that you can paste into your files to extend the context menu in browse mode.
## fmAutomate Services

[fmAutoMate Services](fmautomate-services.html) are Mac OS services that you can install into the Mac OS Services menu to add functionality to text fields and editors anywhere on your computer that text services are supported.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmAutoMate Context Menus]: fmautomate-context-menus.html
