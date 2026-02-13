---
title: fmWorkMate Settings
strapline: Plugins, Options & co.
parent: Setup fmWorkMate
nav_order: 01
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Use the fmWorkMate Settings to setup fmWorkMate.

## Open the Settings

Press <kbd>CMD</kbd><kbd>9</kbd>
: in fmWorkMate (or, indeed, in most of [MrWatson's Tools])

Select `Settings`
: from the `fmWorkMate` menu

Click the `⚙️` button
: at the bottom of the fmWorkMate tool list.

![fmWorkMate Settings > Plugins](/assets/images/fmworkmate-settings-plugins.png)

In the Settings dialog you can

- [Install the Plugins](#install-the-plugins) that fmWorkMate needs
  - and optionally [install the MBS Saxon extension](#install-mbs-saxon-extension-if-desired) for advanced XML processing
- [autofocus FileMaker](#autofocus-filemaker) when generating code.
- set [various options](#more-settings), like keeping fmWorkMate open.
- add your own functions in the [Simple Calculator Settings](#simple-calculator-settings)

## Install the Plugins

You'll need

- The [Base Elements Plugin](https://github.com/GoyaPtyLtd/BaseElements-Plugin/tree/main/docs)
- The [MBS Plugin]

1. [Download the Base Elements plugin](https://github.com/GoyaPtyLtd/BaseElements-Plugin/blob/main/docs/Downloads.md) and place it in FileMaker's extensions folder.
2. [Download the MBS plugin](https://www.monkeybreadsoftware.com/filemaker/) and place it in FileMaker's extensions folder.
3. License the MBS Plugin

   Press `[MBS BYOL]`
   : to register the MBS plugin (BYOL = Bring Your Own License)

   Paste
   : your `MBS ("Register" ; … )` function into the first field in order to automatically fill the fields

   Or use the fields
   : to enter your licence details manually

   `[Register MBS]`
   : to register the plugin for this session.

4. Store the License permanently and safely

    Navigate
    : to the second panel using the slider dots at the bottom

   `[Store License]`
   : to store the MBS registration details permanently

   `[Clear Data]`
   : to remove the MBS registration details from the fields

   `[Clear Stored License]`
   : removes the permanent MBS registration details, should you change your mind later.

## Install MBS Saxon extension, if desired

If you wish to use modern XPath, XSLT or XQuery technologies, you'll need the Saxon library extension for the MBS plugin.

fmWorkMate comes with a (possibly outdated) copy of the Saxon libraries. If you think this is the case, or if the Saxon library is not present in the container filed, first download the latest copy of the Saxon library and place it in the appropriate field on the settings page.

{: .side-note}
The installation process is still in development (and buggy), so if neessary please export the Saxon library file and manually place it in the extensions folder.

Once the Saxon library is in place in the extensions folder…

Press `[Load Saxon]`
: to load the Saxon library

Press `[Saxononica BYOL]`
: to register the Saxon library

Paste your `MBS ("Saxon.Register" ; … )`
: function into the first field in order to automatically fill the fields, or

Use the fields
: to Enter your licence details manually

Press `[Register]`
: to register the extension for this session.

## Autofocus FileMaker

When generating code in fmWorkMate it's possible to get fmWorkMate to bring the FileMaker application of your choice to the foreground automatically.

On the FileMaker tab, 

- Select `[x] Autofocus FileMaker`, if you want to bring FileMaker back to the foreground automatically, When you generate some code in fmWorkMate.
- Choose the FileMaker you want to target for your development work.

![fmWorkMate Settings > FileMaker](/assets/images/fmworkmate-settings-filemaker.png)

## More Settings

- Keep fmWorkMate open
  - Select `[x] Keep fmWorkMate open` if you want fmWorkMate to stay open when opening tools.
- Backdrop
  - Select `[x] Backdrop` to add a backdrop in the given colour whilst working in fmWorkMate.
  - Great, if you want a clear desktop, but, honestly, this is only really useful for screenshots of fmWorkmate. :D

## Simple Calculator Settings

Here you can add your own functions to the [fmSimpleCalculator] tool.

The functions here reachable from the Simple Calculator by just entering an `f`.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmSimpleCalculator]: fmsimplecalculator.html
[MBS Plugin]: mbs-plugin.html
[MrWatson's Tools]: mrwatsons-tools.html
