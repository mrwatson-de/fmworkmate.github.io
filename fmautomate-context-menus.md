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

![MBS Plugin](mbs-plugin.png){: .float-front-right .w-32}
![Mac only](mac-only.png){: .float-front-right .w-32}

{: .important}

This functionality is [Mac only] and requires the [MBS Plugin]!

Having [installed fmAutoMate](fmautomate.html#install-fmautomate) you have some extra context menus in your FileMaker GUI.

![MBS Plugin Script Workspace Context Menu](/assets/images/mbs-context-menu-script-workspace.png){: .float-front-right}

## An Extension of MBS Context Menus

If you use the [MBS plugin] you may have already noticed the MBS right click menu:

This itself provides some very useful functions, particularly…

- `Copy Selection` copies the selected text - the *script workspace step text* - to the clipboard.
- `Enable/Disable` is also useful - at least for German keyboard users - for whom the standard shortcut does not always work.

…but the MBS packs some cool functions to extend this menu and shortcut keys ('hotkeys')

## fmAutoMate Script Workspace Context Menu

{: .mrw-green-bg}
fmAutoMate extends the fantastic MBS Context Menu functionality bringing you extremely powerful tools to your fingertips.

![fmAutoMate Script Workspace Context Menu](/assets/images/fmautomate-script-workspace-context-menu.png){: .float-front-right .clear}

In the Script Workspace right clicking in the script steps area reveals an extended context menu, something like this…

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

![fmAutoMate Layout Workspace Context Menu](/assets/images/fmautomate-layout-workspace-context-menu.png){: .float-front-right .clear}

In the Layout Workspace right clicking on the layout surface area reveals an extended context menu, something like this…

The submenus in the Layout Workspace are basically the same as those in the Script Workspace.

{: .clear}

## fmAutoMate Browse Mode Context Menu

There is even a context menu in Browse mode.

![fmAutoMate Layout Workspace Context Menu](/assets/images/fmautomate-layout-workspace-context-menu.png){: .float-front-right .clear}

Right clicking in browse mode reveals the context menu, and is extended by fmAutoMate something like this…

The submenus in Browse Mode are again basically the same as those in the Script Workspace.

If the [fmAutoMate fmAM Script Module] is installed, you will see further menu entries here.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmAutoMate fmAM Script Module]: fmautomate-fmam-script-module.html
[Mac only]: mac-only.html
[MBS Plugin]: mbs-plugin.html
