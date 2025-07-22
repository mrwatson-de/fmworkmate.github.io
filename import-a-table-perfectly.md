---
title: Import a Table Perfectly
strapline: The devil is in the detail
parent: Solutions to Daily Problems
nav_order: 700
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## Introduction

So…

- you've built your table into the wrong file?
- or you're refactoring your database and a table has to move to a new home?
- or maybe you're building some new functionality into a customer's old version of your database?

No problem! FileMaker has an import table function! All I have to do is…

1. Import the table from the source file
2. Redirect existing Table Occurrences (TOs) to the new table
3. and I'm done!

That's good, *isn't it?*

Well, it depends, but, no, not really very.

## The Problems

There are several potential pitfalls and problems…

- Fields which use custom functions can break
- Fields which reference relationships can break
- Existing field references can break, if the internal field IDs change
- If existing field references break, there can be *a lot of* cleanup work to do in scripts and layouts
- A further problem that can occur is Imposter PTOs (see [Imposter PTOs](imposter-ptos.html))


You have the choice of two evils:

1. You can import a table
   - ✅ this maintains the internal field IDs
     - which means that when you change existing TOs to the new table, all(*) existing field references will be correct
   - ❌ but breaks any calculations that refer to relationships to the table.
     - which may be a lot of work to fix (and find… since field validation and container path calculations may also be broken)
2. You can re-create the table by copying and pasting the fields
   - ✅ this maintains the calculations (but only if done right‼️)
   - ❌ but may change the internal field IDs
     - which means that when you change existing TOs to the new table, you may up with spagehetti code, since existing field references may now reference a completely different field -> and *THAT* could be a nightmare to fix
A missing ID in the source fields is like a missing tooth in a zipper. The teeth don't line up and the zipper won't close.

![Zip IDs together](/assets/images/zipper-up-missing-tooth.png)

![Zip IDs together](/assets/images/zipper-up.png)

## MrWatson's Solution

My solution is a very specific - even scientific - method of importing a table perfectly, which proves (99.9%) you have no errors!

Here is a short summary - I'll flesh it ot later.

1. Kill those pesky default fields with [fmKillDefaultFields] to prevent any internal field IDs from being used.
2. Prepare the target file with all necessary base functionality
   - add any missing external file references
   - add any missing custom functions
   - add any missing referenced fields
3. Create an empty table in the target file.
4. Copy you fields and undelete field number 1 and paste it into the new table
5. Create all related TOs + make dummy relationships to them from field 1
6. Check the related TO names using [fmDBAnalyser]
7. Close the DB definition window
8. Repeat until no errors…

   - Copy you fields and undelete from field 2 to fill those holes in the source field IDs.
   - Paste the fields into the new table and then *without closing the database definition dialog*…
     - Check the `import.log` using [fmLogAnalyser] to verify that no errors occurred
     - If errors occurred,
       - cancel the database definition dialog 
       - fix the errors using fmLogAnalyser as a to do list
       - repeat until no more errors occur
   - Click OK to close the database definition dialog. 

9. Fix the relations hips
10. Check the relationship criteria using [fmDBAnalyser]
11. Fix field 1 if necessary

The table is created! Now 

1. Change old TOs to point to the new table
2. Correct Go to Related Record steps as necessary
3. Test

…and you're done. 😎

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmDBAnalyser]: fmdbanalyser.html
[fmKillDefaultFields]: fmkilldefaultfields.html
[fmLogAnalyser]: fmloganalyser.html
