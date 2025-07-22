---
title: yEd Graphing Tool
strapline: Connect the dots
parent: fmGraphIt
nav_order: 30
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

yEd is a free graphing tool from [yWorks](https://www.yworks.com/products/yed) which can be used to display the field dependencies of your FileMaker database tables.

You need to download, install and setup the yEd editor.

## Download, Install and Setup yEd

- Download and install the free yEd editor from the [yWorks yEd Editor download page]
- Move the app file to your applications folder

You need to set up yEd to be able to format the field dependency graph produced by the [fmCheckMate-XSLT] library.

yEd formats data from a graphml file using a `Property Mapper`. The Properties mapper needs to be configured

### To configure the Property Mapper

- Open yEd
- From the menus select `Edit > Properties Mapper...`
- Press the green down arrow button to import additional configurations.
- Navigate to the `~Documents/fmCheckMate/xml/yEd/fmFieldDependencyGraph` Folder
- Load the latest `FDG_yEdPropertyMap*.cnfx` file.
- Press `[Ok]` to exit

## Getting Started

Once you're set up, you can transform your fields into a stunning diagramme with just a few clicks

1. Copy the (important) fields of a table
2. Convert to XML with [fmCheckMate]
3. Transform to a graphml Field Dependency Graph
4. Open it in your favourite Graphing Tool - [yEd] - to display the graph

   Just a dot?

   Not a problem!

5. Fire up the property mapper
6. Apply the standard style
   - and maybe an alternative color pallette
7. And apply a layout-strategy
   - Try a one-click layout
   - Organic - to discover the complex bits
   - Hierarchy (Left to Right) - 

et voila!

## Learn to Zoom and Navigate

## Explore the different Layouts

## Extract local views of nodes

Want to focus on a particular field?

- Select it
- Choose one of the Context Views fro the Window menu:
  - Neighbourhood - shows the input / output fields around the selected field
  - Predecessors - shows the tree of input fields which feed the selected field
  - Successors - shows all the output fields of the selected field


     :

Enjoy!

MrWatson

[yWorks yEd Editor download page]: https://www.yworks.com/products/yed/download#download