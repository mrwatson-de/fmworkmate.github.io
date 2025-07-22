---
title: MrWatson's Popover Card Window Technique
strapline: Nice
parent: Tips, Tricks and Techniques
nav_order: 0100
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

Here's a handy little thing.

For a FileMaker based email client I needed to be able to choose from the list of folders in three different places on the layout to implement the following three functions:

1. Display contents of «choose folder» (displayed top right)
2. Move an email to «choose folder» (displayed to the right in the record)
3. Move all emails to «choose folder» (displayed at the top of column)

The initial solution of a popover for each of these three functions lead to a terrible repetition of a complicated selection portal, so I needed to find a way of centralising the code.

A card window seemed to be the sensible solution - but I didn't want to lose the intelligent and intuitive positioning of the popover.

The solution was MrWatson's Popover Card Window Technique.

- A card window whose position is guided by an underlying popover button.
- Simply
  - create an _empty_ popover
  - trigger a script when the popover appears, and pass the name of the popover object
  - read the coordinates of the popover object
  - adjust the positioning to taste
  - on close window, don't forget to also close the empty popover
