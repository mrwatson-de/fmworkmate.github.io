---
title: fmAutoMate Context Menus
strapline: for Script Workspace, Layout Mode & Browse Mode
parent: fmAutoMate
nav_order: 0100
layout: default

---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

This functionality is [Mac only] and requires the [MBS Plugin]!

Having [installed fmAutoMate](fmautomate.html#install-fmautomate) you have some extra context menus in your FileMaker GUI.

![MBS Plugin Script Workspace Context Menu](/assets/images/mbs_context_menu_script_workspace.png){: .float-front-right}

## An Extension of MBS Context Menus

If you use the MBS plugin you may have already noticed the MBS right click menu:

This itself provides some very useful functions, particularly…

- `Copy Selection` copies the selected text - the *script workspace step text* - to the clipboard.
- `Enable/Disable` is also useful - at least for German keyboard users - for whom the standard shortcut does not always work.

…but the MBS packs some cool functions to extend this menu - and shortcut keys ('hotkeys') - further, and 

{: .mrw-green-bg}
fmAutoMate extends the fantastic MBS Context Menu functionality bringing you extremely powerful tools to your fingertips.


## fmAutoMate Script Workspace Context Menu

In the Script Workspace right clicking in the script steps area reveals an extended context menu, something like this…

![fmAutoMate Script Workspace Context Menu](/assets/images/fmautomate-script-workspace-context-menu.png)

Under the `fmAutoMate > …` submenus you can find a small description of each of the menu items.

The basic structure is…

fmAutoMate
: help submenus

ChatGPT
: Query ChatGPT to get help with your scripts **Under Construction**

Clipboard
: The main clipboard functions like [Xut, Xopy and PaXte](fmautomate-xopy-n-paxte.html)

Clipboard Copy
: Functions to copy FileMaker things to the clipboard

Clipboard Paste
: Functions to paste things into FileMaker

Code
: Submenus to Analyse, Fix, Multiply, Refactor, Load/Save Snippets of code

Debug
: Functions for debugging

Find & Replace
: Find and or Replace in the XML of your scripts

fmIDE
: Amazing functions made possible only when fmIDE is installed in the file

fmScriptWorkspace
: (Deprecated) functions made possible only when fmScriptWorkspace is installed in the file

HotKeys
: Functions that are usually triggered by a hot key

MBS Toggle
: Toggle lots of MBS options here

Navigate
: Navigate between windows, layouts or even FileMaker versions

Test
: Use this menu to test your own fmAutoMate functionality

zzz
: If displayed, it's a bunch of sleeping or unimportant stuff - best not to touch!

## fmAutoMate Layout Workspace Context Menu

In the Layout Workspace right clicking on the layout surface area reveals an extended context menu, something like this…

![fmAutoMate Layout Workspace Context Menu](/assets/images/fmautomate-layout-workspace-context-menu.png)

The submenus in the Layout Workspace are basically the same as those in the Script Workspace.

## fmAutoMate Browse Mode Context Menu

There are even context menus in Browse mode.

At the bottom of the standard  right clicking on the layout surface area reveals an extended context menu, something like this…

![fmAutoMate Layout Workspace Context Menu](/assets/images/fmautomate-layout-workspace-context-menu.png)

The submenus in Browse Mode are again basically the same as those in the Script Workspace.

If the fmAM Script module is installed, you may see further menu entries here.

{% comment %}mrwMarkdownLinks{% endcomment %}
[Mac only]: mac-only.html
[MBS Plugin]: mbs-plugin.html
