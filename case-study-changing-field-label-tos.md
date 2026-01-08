---
title: Changing Field Labels to a Standard TO
strapline: fmTextConverter, fmAutoMate, fmIDE, Cross Check
parent: Case Studies
nav_order: 0200
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## The Problem

At Günther Business Solutions in the Advanter® ERP System multilinguality is achieved using global fields from the central language table - `Advanter.SYS_Sprache_glob`.

This is a simple system in which the users langauge is loaded at logon and each label is a simple global field.

However, development over many years has - for one reason or another - slightly complicated the situtuation

### Too many TOs

1. Originally only the table `Advanter.SYS_Sprache_glob` was used.
2. In some modules a second TO was used to distinguish the elements and labels belonging to that module, for example for the returned-goods module we had `Reklamation.SYS_Sprache_glob`.
3. Finally, when buttons arrived in FileMaker we introduced a second TO - simply `L` - to help shorten field references within button labels.

Now we have three TOs, where actually only one is necessary? It was time to tidy up this mess!

The challenge was…

- how to discover which objects were using the `Reklamation.SYS_Sprache_glob` and `L` TOs,
- how to efficiently navigate to the layouts.
- how to locate the label objects on the layouts quickly.
- how to change the TOs of the - potentially very many - objects quickly and without error.
- how to quickly 'tick off' the objects as being completed.

## The Solution

A number of tools came together to solve this problem quickly and efficiently.

### Which objects use the `Reklamation.SYS_Sprache_glob` TO?

We use [Cross Check] to analyse our database, so a quick search in the Layout Objects table for objects referencing the `Reklamation.SYS_Sprache_glob` TO showed us that there were hundreds of such objects scattered across multiple layouts.

### Navigating to the layouts & objects quickly

The saving grace here is [fmIDE] & the [Go to fmThing] script in Cross Check.

Both advanter and Cross Check are [fmIDE enbabled]. That means that the fmIDE Script is built into every advanter solution file, and that (our version of) Cross Check has a [Go to fmThing] script to jump straight to the current thing in the target solution files.

<kbd>⇧⌘M</kbd>
: Jump to the current fmThing (using fmIDE)

That's it.

1. One keypress and you are there.
2. Now just change into Layout mode and
3. Do your evil work

### Preparing fmTextConverter to convert the TO Names

Since there were more that one table names needing replacement, using fmTextConverter was a natural choice.

The following conversions were set up in fmTextConverter to change the other TOs to the simple `L` TO:

| Search                         | Replace   |
|--------------------------------|-----------|
| `Reklamation.SYS_Sprache_glob` | `L`       |
| `Advanter.SYS_Sprache_glob`    | `L`       |

### Converting Multiple Labels to a Standard TO

Now that everything is set up, there is a magic process to convert multiple labels quickly and efficiently:

Iff the labels are on the layout or on a 

1. Enter Layout Mode (<kbd>⌘L</kbd>)
2. Select & cut all the visible labels from the layout (<kbd>⌘X</kbd>)
3. Convert using fmTextConverter
   - <kbd>⌘TAB</kbd> Swap to fmTextConverter
   - <kbd>⌘6</kbd> FM → Conveert → FM
   - <kbd>⌘TAB</kbd> Swap back to FileMaker
4. Paste the converted labels back onto the layout **in the original position**
   - Reset the layout's default positioning by switching to browse mode and back  (<kbd>⌘B</kbd><kbd>⌘L</kbd>)
   - Paste the converted labels onto the layout (<kbd>⌘V</kbd>)

### Converting Single Labels to a Standard TO

Where there is only one or two labels to change the TO, MBS can help

- Double Click the label to open the field picker dialog.
- The first time you will have to choose the target TO manually,
- On further fields you can use the MBS Button above the relationship name to change the TO in a single click.

### Rinse and Repeat

To check what TOs are still in use to see if you are finished in the current layout, rather than tediously toggling between the FileMaker databae and Cross Check, it is much simpler just to use FileMaker's Sort Records dialog (<kbd>⌘S</kbd>), which lists all the fields on the layout.

Still seeing `Reklamation.SYS_Sprache_glob` or `Advanter.SYS_Sprache_glob` in the list?

Just close the dialog, rinse and repeat the above until you have finished.

### Ticking off completed objects in Cross Check

Once finished you *could* just switch to Cross Check and omit each object that you have completed from the results, but … **wouldn't it be better if you could just right click on the Layout name and use FileMaker's `Omit matching records` command?**

That would be fantastic!

Oh yes, - they haven't get round to implementing that exceptionally useful function yet.

fmAutoMate, on the other hand, has an ace up its sleeve, for just this occasion!

As you may know, fmAutoMate already adds some great (calculation engine based) functionality to right click menus in your FileMaker GUI.

Not only in the script workspace, but also in browse mode.

Now just add the fmAM fmAutoMate Script Module, and you have exactly the function you need.

Not only `Omit matching records`, but also `Find/Constrain/Extend matching records`, **and** with the <kbd>ALT</kbd> key held down you can get the `(==) match whole field` option to boot!


So, where was I, oh yes, moving on to the objects in the next layout in Cross Check.

<kbd>⇧⌃2</kbd>
: Swap back to the second window (that is: Cross Check)

<kbd>Right-Click</kbd>
: `Omit matching records (==)` to omit all the object records for this layout.

<kbd>⇧⌘M</kbd>
: Go to Thing - the first label object of the next layout (using fmIDE deep linking)


### Rinse and Repeat

Et voilá, you are back in FileMaker on the next layout, ready to repeat the process.

Let me know how you get on!

MrWatson
