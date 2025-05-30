---
title: Dock Script Window to Script Workspace
strapline: You don't need to get stuck in a GUI dead-end!
parent: Solutions to Daily Problems
nav_order: 1300
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## Introduction

FileMaker has a pretty neat debugger, with a very useful button for editing the current script, which allows you to open the script and break off the debugging. It's a quick way to get to a script directly from a button or process,… **however…**

## The Problem

when you edit the currently running script, you get a standalone editing window for editing the steps of the script, which lacks many of the niceties of being in the script workspace. For example, you are not able to see where the script is in the script tree, or to duplicate the script.

Morevover, there is no way to easily get back to editing this script in the Script Workspace, other than closing the window, opening the Script workspace and going to find the same script (and good luck with that!)

You get stuck in a bit of a GUI dead-end, which doesn't feel nice - even the 100th time you find yourself there

## MrWatson's Solution

Two of MrWatson's integration tools to the rescue!

1. [fmAutoMate](./fmautomate.html)
2. [fmIDE](./fmide.html)

Having installed fmAutoMate in the current FileMaker and having built fmIDE into your solution files, you simply right click in the script editing window to show the fmAutoMate menu and select `fmIDE > Dock Window to Script Workspace`, and the script window will be docked to the script workspace.

![Right-click > fmIDE > Dock Window to Script Workspace](/assets/images/fmautomate-dock-script-window-to-script-workspace.png)