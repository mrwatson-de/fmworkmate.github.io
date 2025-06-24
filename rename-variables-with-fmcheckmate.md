---
title: Rename variables with fmCheckMate
strapline: Quick and easy
layout: default
parent: fmCheckMate
nav_order: 0100
---
1. TOC
{:toc}

{% include page-image.html width="400" %}

# {{page.title}}

{{page.strapline}}

{: .side-note .float-front-right}
You can do this even more quickly and intuitively with [fmAutoMate]!

You can quickly rename script variables using fmCheckMate:

1. Copy (or cut) all the script steps where the variable is used
2. Open [fmCheckMate]
   - from [fmWorkMate] <kbd>⌘</kbd><kbd>2</kbd>
3. Convert to XML
   - by clicking [`Convert Clipboard`]
   - or pressing <kbd>⌘</kbd><kbd>2</kbd>
4. Type the <kbd>$old name</kbd> of the variable to search for - including the $.
5. Press <kbd>⇥</kbd> (or <kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>) and enter the <kbd>$new_name</kbd> - including the $.
6. To replace and convert back to FileMaker objects on the clipboard
   - either
     - Click `[R]` or press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>A</kbd> to replace **a**ll and
     - Click `[→ FM]` or press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>V</kbd> to convert back to the FileMaker clipboard
   - or
     - Press <kbd>⌥</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>V</kbd> (for replace **a**ll) to do it in one keypress
7. In FileMaker paste the changed code back into your FileMaker script workspace.

This process helps ensure consistent and error-free variable renaming throughout your scripts.

## Killer keyboard mode

### To rename variables

{: .fullwidth .mrw-killer-bg}

FileMaker <kbd>⌘</kbd><kbd>X</kbd> • fmWorkMate <kbd>⌘</kbd><kbd>2</kbd> • fmCheckMate <kbd>⌘</kbd><kbd>2</kbd> • <kbd>$old name$</kbd> • <kbd>⇥</kbd> • <kbd>$new_name</kbd> • <kbd>⌥</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>V</kbd> • FileMaker <kbd>⌘</kbd><kbd>V</kbd>

alternatively, using the fmCheckMate **c**onvert clipboard shortcut key:

{: .fullwidth .mrw-killer-bg}

fmCheckMate <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd> • <kbd>$old name$</kbd> • <kbd>⇥</kbd> • <kbd>$new_name</kbd> • <kbd>⌥</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>V</kbd>


### To repeat the last replacement

…you can use the menu option or shortcut key:

{: .fullwidth .mrw-killer-bg}

`XML Editor` > `Edit XML` > `FM → Replace All → FM Clipboard` <kbd>⌥</kbd><kbd>⇧</kbd><kbd>⌘</kbd><kbd>C</kbd>

{% comment %}mrwMarkdownLinks{% endcomment %}
[FileMaker]: filemaker.html
[fmAutoMate]: fmautomate.html
[fmCheckMate]: fmcheckmate.html
[fmWorkMate]: fmworkmate.html
