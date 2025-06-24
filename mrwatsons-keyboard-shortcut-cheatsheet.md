---
title: MrWatson's Keyboard Shortcut Cheatsheet
strapline: All the keys
parent: Help
nav_order: 1000
layout: default
---
- TOC
{:toc}

{% include page-image.html width="100" %}

# {{page.title}}

{{page.strapline}}

This cheatsheet lists all the useful keyboard shortcuts (and mouse clicks) to get things done quicker within the FileMaker Developer Environment (GUI). It presents the combined shortcuts and functionality from 

- Operating System
- [FileMaker Pro](filemaker-pro.html)
- [MBS Plugin](mbs-plugin.html)
- [fmAutoMate] 

### Notes

![Command-Ctrl](/assets/images/ctrl-cmd.png){:.w-64 .clear .float-front-right}

{: .mrw-windows-bg}
Of course windows users will need to use the ctrl key <kbd>⌃</kbd> instead of the command key <kbd>⌘</kbd>.

For example to search in the relationship graph, use <kbd>Ctrl</kbd>+<kbd>F</kbd> instead of <kbd>⌘</kbd>+<kbd>F</kbd>.

{: .mrw-killer-bg }
MrWatson's tools and the MBS Plugin optimize the interactive experience for power keyboard users. See [Killer Keyboard Mode](killer-keyboard-mode.html) for the details.

Note that the modifier keys tend to be used with the following meanings:

<kbd>⇧</kbd>
: The shift key often means "backwards" or "do it *the other* way" \
(as in <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd> Find again backwards)
: or it simply indicates the key is an upper character on the keyboard \
(as in <kbd>⇧</kbd><kbd>⌘</kbd><kbd>=</kbd> for fmSimpleCalculator)

<kbd>⌥</kbd>
: The option (alt) key often means: "do it in a different, *alt*ernative way".

See also the [Useful Links](#useful-links) at the bottom of this page

{: .mrw-orange-bg .clear}
Please let me know if there is anything missing from or incorrect on this page

## General Keys

| In this environment        | In this context           | Do/press this                              | In order to                         |
| -------------------------- | ------------------------- | ------------------------------------------:| ----------------------------------- |
| Mac                        | editible Lists            | <kbd>⌃</kbd><kbd>↑</kbd>/<kbd>↓</kbd> | Move selected element(s) in list <sup><a href="#fn-1" id="fnref-1">1</a></sup> |
| Win                        |                           | <span class="win"><kbd>⌃</kbd><kbd>↑</kbd>/<kbd>↓</kbd></span> |                 |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>C</kbd>                   | Copy content                        |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>F</kbd>                   | Find in list                        |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>G</kbd>                   | Find again in list                  |
| Mac + MBS                  | Most List Dialogs         | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd>       | Find again backwards inlist         |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>+</kbd>                   | Zoom in.                            |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>-</kbd>                   | Zoom out.                           |
| Mac + MBS                  | Most List Dialogs         | <kbd>⌘</kbd><kbd>=</kbd>                   | Zoom to 100%.                       |
| Mac + MBS                  | Most List Dialogs         | <kbd><samp>Right-click</samp></kbd>        | Show MBS Context Menu               |
| Mac + MBS                  | Text Area                 | <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd>       | copies styled text.                 |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>]</kbd>                   | shift text to right.                |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>[</kbd>                   | shift text to left.                 |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>F</kbd>                   | shows find bar.                     |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>G</kbd>                   | goes to next found text.            |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>R</kbd>                   | shows rulers.                       |
| Mac + MBS                  | Text Area                 | <kbd>⌘</kbd><kbd>I</kbd>                   | shows invisible characters          |
| Mac + MBS + **fmAutoMate**     | **fmAutoMate** HotKeys ON     | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>K</kbd>       | Open **fmAutoMate**´s Extended HotKeys dialog |
| Mac + MBS + **fmAutoMate**     | Most Dialogs + Workspaces | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>X</kbd>       | Xut - Cut as XML                    |
| Mac + MBS + **fmAutoMate**     | Most Dialogs + Workspaces | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>C</kbd>       | Xopy - Xopy as XML                  |
| Mac + MBS + **fmAutoMate**     | Most Dialogs + Workspaces | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>V</kbd>       | PaXte - Paste XML                   |


<sup><a href="#fnref-1" id="fn-1">1</a></sup> Note: You may have to turn off the OS Mission Control shortcuts which clash with <kbd>⌃</kbd><kbd>↑</kbd> / <kbd>⌃</kbd><kbd>↓</kbd>.


## Script Workspace Keys

| In this environment    | In this context | Do/press this                                          | In order to                         |
| ---------------------- | --------------- | ------------------------------------------------------:| ----------------------------------- |
| Any OS                     | script tab      | <kbd><samp>Right-click</samp></kbd><kbd><samp>Check for Problems</samp></kbd>    | Check script for problems           |
| Mac                        | script step     | <kbd>+</kbd>                                           | Edit script step options            |
| Mac + MBS                  | script step     | <kbd>⌥</kbd><kbd><samp>Double-click</samp></kbd>       | Edit script step calculation        |
| Mac + MBS                  |                 | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>                   | Find in script list                 |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>F</kbd>                               | Find in script step text            |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>F</kbd> then <kbd>Enter</kbd>         | Find again in script step text      |
| Mac + MBS + **fmAutoMate** | script step     | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>F</kbd>                   | Find in script step text                          |
| Mac + MBS + **fmAutoMate** | script step     | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>G</kbd>                   | Find Again in script step text                    |
| Mac + MBS + **fmAutoMate** | script step     | <kbd>⌃</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd>       | Find Again backwards in script step text          |
| Mac + MBS + **fmAutoMate** | selected steps  | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>A</kbd>                   | Replace All in XML of selected steps              |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>G</kbd> or <kbd>⌘</kbd><kbd>L</kbd>   | Go to line in script steps          |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>+</kbd>                               | Zoom in on active area              |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>-</kbd>                               | Zoom out on active area             |
| Mac + MBS                  |                 | <kbd>⌘</kbd><kbd>=</kbd>                               | Zoom active area to 100%            |
| Mac + MBS                  | script step     | <kbd><samp>Right-click</samp></kbd>                    | See a context Menu of MBS functions |
| Mac + MBS + **fmAutoMate** | script step     | <kbd><samp>Right-click</samp></kbd>                    | See a context Menu of **fmAutoMate** functions        |
| Mac + MBS                  | script step     | <kbd><samp>Click</samp> ⌄</kbd>                        | Toggle code block (section)         |
| Mac + MBS                  | script step     | <kbd>⌥</kbd><kbd><samp>Click</samp> ⌄</kbd>            | Toggle code block (entire block)    |
| Mac + MBS                  | Export Records Dialog | <kbd><samp>Hover Tooltip</samp></kbd>            | Useful [Tooltips for the FileMaker export dialog](https://www.mbs-plugins.com/archive/2019-03-07/Tooltips_for_the_FileMaker_exp/monkeybreadsoftware_blog_filemaker) |
| Mac + MBS + **fmAutoMate** | script step     | <kbd><samp>Right-click</samp></kbd> then type <kbd>O</kbd><kbd>N</kbd><kbd>⏎</kbd> | Turn on **fmAutoMate** HotKeys |
| Mac + MBS + **fmAutoMate** | script step     | <kbd>⌃</kbd><kbd>⌘</kbd><kbd>H</kbd>                   | Insert a history comment                          |

## Layout Workspace Keys

| In this environment | In this context | Do/press this                                          | In order to            |
| ------------------- | --------------- | ------------------------------------------------------:| ---------------------- |
| Mac + MBS           |                 | <kbd>⌥</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>       | Find object in layout. |

## Calculation & Custom Function Editor Keys

| In this environment | In this context | Do/press this                                                       | In order to             |
| ------------------- | --------------- | -------------------------------------------------------------------:| ----------------------- |
| Mac + MBS           |                 | <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd>                                | Copy MBS-styled text    |
| Mac + MBS           |                 | <kbd>⌘</kbd><kbd>F</kbd>                                            | Show + Enter Find Field |
| Mac + MBS           |                 | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>                                | Enter Replace Field     |
| Mac + MBS           |                 | <kbd>⌘</kbd><kbd>G</kbd>                                            | Find Again              |
| Mac + MBS           |                 | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd>                                | Find Again Backwards    |
| Mac + MBS           |                 | <kbd>⌘</kbd><kbd>]</kbd> or<br><kbd>⌥</kbd><kbd>⌘</kbd><kbd>5</kbd> | Indent selected text    |
| Mac + MBS           |                 | <kbd>⌘</kbd><kbd>[</kbd> or<br><kbd>⌥</kbd><kbd>⌘</kbd><kbd>6</kbd> | Outdent selected text   |
| Mac + MBS           |                 | <kbd>⌥</kbd><kbd>⌘</kbd><kbd>I</kbd>                                | Toggle invisible characters<br>MBS < 15.2: without <kbd>⌥</kbd>|
| Mac + MBS           |                 | <kbd>⌥</kbd><kbd>⌘</kbd><kbd>R</kbd>                                | Show Ruler / Temporarily edit tab stops<br>MBS < 15.2: without <kbd>⌥</kbd> |
| Mac + MBS           |                 | <kbd>⌘</kbd><kbd>T</kbd>/<kbd>N</kbd>/<kbd>D</kbd>/<kbd>I</kbd>/<kbd>M</kbd>/<kbd>R</kbd> | Set the data type (like in the field list) |
| Mac + MBS           |                 | <kbd>⌃</kbd><kbd>[</kbd>/<kbd>]</kbd> | Indent / outdent selected text |
| Mac + MBS           |                 | <kbd>⌃</kbd><kbd>↑</kbd>/<kbd>↓</kbd> | Move selected text up / down |

## Debugger Keys

| In this environment | In this context | Do/press this                                          | In order to             |
| ------------------- | --------------- | ------------------------------------------------------:| ----------------------- |
| Mac                 |                 | <kbd>F5</kbd>                                          | Step Over               |
| Mac                 |                 | <kbd>⇧</kbd><kbd>⌘</kbd>F5</kbd>                       | Set Next Step           |
| Mac                 |                 | <kbd>F6</kbd>                                          | Step Into               |
| Mac                 |                 | <kbd>F7</kbd>                                          | Step Out                |
| Mac                 |                 | <kbd>⌘</kbd>F8</kbd>                                   | Halt Script             |
| Mac                 |                 | <kbd>⌥</kbd>F8</kbd>                                   | Continue                |
| Mac                 |                 | <kbd>⌘</kbd>F9</kbd>                                   | Set Breakpoint          |
| Mac                 |                 | <kbd>⇧</kbd><kbd>⌘</kbd>F9</kbd>                       | Remove Breakpoint       |
| Mac                 |                 | <kbd>⌘</kbd>F10</kbd>                                  | Edit Script             |

## Data Viewer Keys

| In this environment | In this context   | Do/press this                                        | In order to                  |
| ------------------- | ----------------- | ----------------------------------------------------:| ---------------------------- |
| Mac + MBS           | focus on the list | <kbd>⌘</kbd><kbd>F</kbd>                             | Show + Enter Find Field      |
| Mac + MBS           | focus on the list | <kbd>⌘</kbd><kbd>G</kbd>                             | Find Again                   |
| Mac + MBS           | focus on the list | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd>                 | Find Again Backwards         |
| Mac + MBS           | focus on the list | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>                 | Show/hide fields.            |
| Mac + MBS           | focus on the list | <kbd>⇧</kbd><kbd>⌘</kbd><kbd>G</kbd>                 | Show/hide global variables.  |
| Mac + MBS           | focus on the list | <kbd>⌘</kbd><kbd>+</kbd>                             | Zoom in.                     |
| Mac + MBS           | focus on the list | <kbd>⌘</kbd><kbd>-</kbd>                             | Zoom out.                    |
| Mac + MBS           | focus on the list | <kbd>⌘</kbd><kbd>=</kbd>                             | Zoom to 100%.                |
| Mac + MBS           | focus on the list | <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd>                 | Copy text in the list.       |

## Relationship Dialog Keys

| In this environment | In this context       | Do/press this                                    | In order to                       |
| ------------------- | --------------------- | ------------------------------------------------:| --------------------------------- |
| Mac                 | relationship selected | <kbd>⌘</kbd><kbd>O</kbd>                         | Open the Edit Relationship dialog |
| Mac + MBS           |                       | <kbd>⌘</kbd><kbd>F</kbd>                         | Set focus to search field.        |

## Useful Links

- [Claris Pro and FileMaker Pro Help > Reference > Keyboard shortcuts (macOS)](https://help.claris.com/en/pro-help/content/shortcuts-os-x.html)
- [Claris Pro and FileMaker Pro Help > Reference > Keyboard shortcuts (Windows)](https://help.claris.com/en/pro-help/content/shortcuts-windows.html)
- [Mac keyboard shortcuts](https://support.apple.com/en-us/HT201236)
- [Create keyboard shortcuts for apps on Mac](https://support.apple.com/en-gb/guide/mac-help/mchlp2271/mac)

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmAutoMate]: fmautomate.html
