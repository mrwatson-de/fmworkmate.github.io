---
title: fmCheckMate Modes
strapline: Convert/Transfer, Analyse/Fix or Edit/Transform your FileMaker work
parent: fmCheckMate Settings
nav_order: 0020
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmCheckMate has a few different modes of operation to match your current activities.

![Settings Button](/assets/images/fmcheckmate-settings-button.png){:.float-front-right .w-128}

 The current mode is shown in the top right corner of the app window (default is the Small XML Editor). 

<kbd>⌘9</kbd>{: .float-front-right}

## fmCheckmate Settings Wizard

Clicking the current mode indicator opens the fmCheckMate `Settings Wizard` & mode chooser. Alternatively select menu `fmCheckMate > Settings…` or press <kbd>⌘9</kbd>.

![Settings Wizard](/assets/images/fmcheckmate-settings-wizard.png)

You can choose between three main modes of operation:

| Use mode               | When you want to                                                       |
| ---------------------- | ---------------------------------------------------------------------- |
| **Convert & Transfer** | transfer code across a remote connection between FileMaker deployments |
| **XML Editor**         | edit the XML, see, search, change or transform it                      |
| **Analysis**           | check your code - particularly layouts - for errors                    |

<kbd>⌘2</kbd>{: .float-front-right}

## Convert & Transfer Mode

In Convert and Transfer mode when you convert the clipboard between FileMaker objects and fmxmlsnippet text fmCheckMate does not change to the editor view but stays on the home layout

![fmChekMate's Convert and Transfer mode](/assets/images/fmcheckmate-convert-and-transfer-mode.png)

If you want to transfer code across a remote connection between FileMaker deployments, you can use the `Convert & Transfer` mode in fmCheckMate on both machines to quickly move code between them with just a few clicks.

<kbd>⌘3</kbd>{: .float-front-right}

## XML Editor Mode

The XML Editor mode is about working with the XML.

There are four different XML Editor modes to choose from, depending on your needs:

![Mode Buttons 2](/assets/images/fmcheckmate-xml-modes.png)

<kbd>⌘2</kbd>{: .float-front-right}

### Large XML Editor

{: .note}
Interested in the XML?

Use the large XML editor for a full-screen XML editing experience.

<kbd>⌘3</kbd>{: .float-front-right}

### Small XML Editor

{: .note}
Not inteerested in the XML? Just get on with it!

Use the small XML editor for minimal impact on your workspace.

<kbd>⌘4</kbd>{: .float-front-right}

### External XML Editor

{: .note}
Want the full power of a real xml editor?

Use the external XML editor option to export and edit the xml in your default xml editor.

<kbd>⌘5</kbd>{: .float-front-right}

### Int. + Ext. XML Editors

{: .note}
Never could make a decision?

Use both internal and external XML editors.

<kbd>⌘4</kbd>{: .float-front-right}

## Analysis Mode

In Analysis mode when you convert the clipboard fmCheckMate immediately shows the list of analysis functions, so you can choose one to run on the XML.
