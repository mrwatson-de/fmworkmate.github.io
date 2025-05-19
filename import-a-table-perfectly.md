---
title: Import a Table Perfectly
strapline: The devil is in the detail
parent: Solutions to Daily Problems
nav_order: 700
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

### Introduction

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

### The Problems

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

### MrWatson's Solution

Undelete those holes in the source field IDs