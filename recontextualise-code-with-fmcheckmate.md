---
title: Recontextualise code with fmCheckMate
strapline: Same fields, different TO
logo: /assets/images/beermats/beermat-rock-n-roll.png
layout: default
parent: fmCheckMate
nav_order: 400

---
- TOC
{:toc}

{% include page-image.html width="400" %}

# {{page.title}}

{{page.strapline}}

## Problem

Have you got some fields nicely arranged in a portal but you now need to have the same fields shown in a new list layout?

You can copy and paste the fields to the new list layout, but the problem is

- you need to change the TO of every field to the LayoutTable / PTO
- …and every calculation - conditional formatting condition, hide calculation, tip or placeholder calculation also needs to be changed?
- …and every button script parameter also may need changing?

Bummer!

![fmCheckMate](fmcheckmate.png){:.float-front-right .mt-16 .w-64}

## Solution using fmCheckMate

Use fmCheckMate to rename all the TO references in a quick process:

If your portal TO on the `Company List` layout is `Company.Contacts` and your `Contacts List` layout is based on the PTO `_Contacts` then try this:

1. Go to the `Company List` layout and copy the fields in the `Company.Contacts` portal - <kbd>⌘</kbd><kbd>C</kbd>
2. Open fmCheckMate and press the `[Convert Clipboard]` button, or press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd> (for **C**onvert) or <kbd>⌘</kbd><kbd>2</kbd>
3. Type `Company.Contacts` (because the find field is already in focus) and press <kbd>Tab</kbd> or <kbd>⇧</kbd><kbd>⌘</kbd><kbd>F</kbd>
4. Type `_Contacts`
5. Either
   - replace **a**ll occurrences by clicking the `[R]` button or pressing <kbd>⌥</kbd><kbd>⌘</kbd><kbd>A</kbd>
   - convert back to FileMaker objects by clicking the `[→ FM]` button or pressing <kbd>⌥</kbd><kbd>⌘</kbd><kbd>V</kbd>
   or
   - just press <kbd>⇧</kbd><kbd>⌥</kbd><kbd>⌘</kbd><kbd>V</kbd> to replace and convert in one go
6. Go to the `Contacts List` layout and paste the fields in. - <kbd>⌘</kbd><kbd>V</kbd>

{: .fullwidth .mrw-killer-bg}

### Killer keys

<kbd>⌘</kbd><kbd>C</kbd> • <kbd>⌥</kbd><kbd>⌘</kbd><kbd>C</kbd> • «find string» • <kbd>Tab</kbd> «replace string» • <kbd>⇧</kbd><kbd>⌥</kbd><kbd>⌘</kbd><kbd>V</kbd> • <kbd>⌘</kbd><kbd>V</kbd>

### Check your work / Prove you are right

If you have done it all right your fields should now be in the right context, and there should be no errors.

If you are not sure if there are errors, then copy the code back out of the layout and [check it using fmCheckMate's Layout Analysis function](layout-analysis-with-fmcheckmate.html).

![fmAutoMate](fmautomate.png){:.float-front-right .mt-16 .w-64}

## Alternative Solution using fmAutoMate

It is also possible to find and replace to [recontextualise your code directly within FileMaker using fmAutoMate](recontextualise-code-with-fmautomate.html), which is a much more tightly integrated solution.
