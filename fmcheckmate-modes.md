---
title: fmCheckMate Modes
strapline: Convert/Transfer, Analyse/Fix or Edit/Transform your FileMaker work
parent: fmCheckMate Settings
nav_order: 020
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

fmCheckMate has a few different modes of operation to match your current activities.

![Settings Button](/assets/images/fmcheckmate-settings-button.png){:.float-front-right .w-128}

 The current mode is shown in the top right corner of the app window (default is the Small XML Editor). Clicking it opens the fmCheckMate `Settings Wizard` & mode chooser. Alternatively press <kbd>⌘9</kbd> or select menu `fmCheckMate > Settings…`

![Settings Wizard](/assets/images/fmcheckmate-settings-wizard.png)

You can choose between three main modes of operation:

| Use mode               | When you want to                                                       | Shortcut                   |
| ---------------------- | ---------------------------------------------------------------------- | :------------------------: |
| **Convert & Transfer** | transfer code across a remote connection between FileMaker deployments | <kbd>⌘9</kbd><kbd>⌘2</kbd> |
| **XML Editor**         | edit the XML, see, search, change or transform it                      | <kbd>⌘9</kbd><kbd>⌘3</kbd> |
| **Analysis**           | check your code for errors, particularly layouts!                      | <kbd>⌘9</kbd><kbd>⌘4</kbd> |

### Convert & Transfer Mode

In Convert and Transfer mode when you convert the clipboard between FileMaker objects and fmxmlsnippet text fmCheckMate does not change to the editor view but stays on the home layout

If you want to transfer code across a remote connection between FileMaker deployments, you can use the `Convert & Transfer` mode in fmCheckMate on both machines to quickly move code between them.

### Analysis Mode

In Analysis mode, when you convert the clipboard fmCheckMate immediately shows the list of analysis functions, so you can choose one to run on the XML.

### XML Editor Mode

The XML Editor mode is about working with the XML. There are several different XML Editor modes to choose from, depending on your needs:

![Mode Buttons 2](/assets/images/fmcheckmate-xml-modes.png)

| Use XML Editor mode                 | When you want to                                           | Shortcut                                |
| ----------------------------------- | ---------------------------------------------------------- | --------------------------------------- |
| **XML Editor › Large**              | see the XML clearly                                        | <kbd>⌘9</kbd><kbd>⌘3</kbd><kbd>⌘2</kbd> |
| **XML Editor › Small**              | edit the XML with minimal impact on your workspace         | <kbd>⌘9</kbd><kbd>⌘3</kbd><kbd>⌘3</kbd> |
| **XML Editor › Int. + Ext. Editor** | use both internal and external editors                     | <kbd>⌘9</kbd><kbd>⌘3</kbd><kbd>⌘4</kbd> |
| **XML Editor › External**           | edit the xml in your default xml editor                    | <kbd>⌘9</kbd><kbd>⌘3</kbd><kbd>⌘5</kbd> |
