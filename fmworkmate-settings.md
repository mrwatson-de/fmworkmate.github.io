---
title: fmWorkMate Settings
strapline: Plugins, Options & co.
parent: fmWorkMate
nav_order: 05
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

## Install the Plugins

You'll need

- The Base Elements plugin
- The [MBS Plugin]

1. Download the Base Elements plugin and place it FileMaker's extensions folder.
2. Download the MBS plugin and place it FileMaker's extensions folder.
3. License the MBS Plugin

## Install MBS Saxon extension, if desired

If you wish to use modern XPath, XSLT or XQuery technologies, you'll need the Saxon library extension for the MBS plugin.

fmWorkMate comes with a (possibly outdated) copy of the Saxon libraries. If you think this is the case, or if the Saxon library is not present in the container filed, first download the latest copy of the Saxon library and place it in the appropriate field on the settings page.

{: .side-note}
The installation process is still in development (and buggy), so if neessary please export the Saxon library file and manually place it in the extensions folder.

Once the Saxon library is in place in the extensions folder…

Press [Load Saxon]
: to load the Saxon library

Press [Saxononica BYOL]
: to register the Saxon library

Paste your MBS ("Saxon.Register" ; … )
: function into the first field in order to automatically fill the fields, or

Use the fields
: to Enter your licence details manually

Press [Register]
: to register the extension. for this session

## Autofocus FileMaker

When generating code in fmWorkMate it's possible to get fmWorkMate to bring the FileMaker application of your choice to the foreground automatically.

On the FileMaker tab, 

- Select `[x] Autofocus FileMaker`, if you want to bring FileMaker back to the foreground automatically, When you generate some code in fmWorkMate.
- Choose the FileMaker you want to target for your development work.

![fmWorkMate Settings > FileMaker](/assets/images/fmworkmate-settings-filemaker.png)

{% comment %}mrwMarkdownLinks{% endcomment %}
[MBS Plugin]: mbs-plugin.html
[MrWatson's Tools]: mrwatsons-tools.html
