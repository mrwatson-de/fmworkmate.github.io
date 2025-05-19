---
title: fmGraphIt
strapline: Connect the dots
parent: Roadmap
nav_order: 30
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

fmGraphIt helps you visualize the field dependencies of your FileMaker database tables.

**Fed up of trawling though field definitions to understand how fields hang together?**

➡ A picture is worth a thousand words!

  ![Trawling Fields](/assets/images/fmgraphit-a-picture-is-worth-a-thousand-words.png)

Just copy the fields and get the big picture with fmGraphIt in a few clicks!

> Iif you have a FileMaker Database with a table (or two) of unknown, confusing, or down right mysterious fields…
>
> …you need **fmGraphIt**!


## Installing fmGraphIt

fmGraphIt is a process, not a tool.

<a class="anchor" id="1">1</a> **fmGraphIt** is, indeed, not a _seperate_ tool of it's own 😳, rather it is a *process* using some of the tools in MrWatson's toolkit.



## What do you need?

To generate a field dependency graph from the field definitions of one table you will need 

1. MrWatson's **fmWorkMate** toolbox (which includes the **fmCheckMate** tool)

  ![](docs/fmworkmate_and_fmcheckmate.png) 

  - Download the [latest release of fmWorkMate from GitHub](https://github.com/mrwatson-de/fmWorkMate/releases/latest)

2. MrWatson's **fmCheckMate-XSLT Library** (which includes the graph creation function)

  ![](docs/fmCM_XSLT_Folder_128.png) 

  - Download the [latest release of fmCheckMate-XSLT from GitHub](https://github.com/mrwatson-de/fmCheckMate-XSLT/releases/latest)

3. To visualise this field dependency graph you will need a graph visualisation tool. 

- The free **yEd** software from **yWorks**

   ![](docs/yEd_Logo_128.png)

  - Download the [latesyt version of yEd from yWorks](https://www.yworks.com/products/yed)

4. some yEd configuration files for formatting the graph (which are to be found in the xml/yEd folder of The **fmCheckMate-XSLT Library**)

4. Finally, you need

- A step-by-step guide to installing **fmGraphIt** ( **fmWorkMate**, the  **fmCheckMate-XSLT Library**, and yEd)
- A tutorial on creating your first Field Dependency Graph
- A Field Dependency Graph Legend
- An introduction to yEd

## Installing fmGraphIt - Step by Step

You need to download, install ans setup the following components:

1. Download & Install  **fmWorkMate**
2. Download & Install **fmCheckMate-XSLT Library**
3. Setup  **fmWorkMate** & **fmCheckMate**
4. Download & Install yEd
5. Setup yEd

### 1. Download & Install fmWorkMate

Download  **fmWorkMate** from the [fmWorkMate Repo] and follow the installation instructions in the Readme file.

### 2. Download & Install fmCheckMate-XSLT library

Download the  ** fmCheckMate-XSLT Library** from the [fmCheckMate-XSLT Library Repo] and follow the installation instructions in the Readme file.

### 3. Setup fmWorkMate & fmCheckMate

You need to 

- Follow the instructions in the **fmWorkMate** Readme to setup the MBS and Base Elements plugins in the **fmWorkMate** Settings page (i)
- In **fmCheckMate** load the XSLT

### 4. Download & Install yEd

- Download and install the free yEd editor from the [yWorks yEd Editor download page]
- Move the app file to your applications folder

### 5. Setup yEd

The Properties mapper needs to be configured

- From the menus select `Edit > Properties Mapper...`
- Press the green down arrow button to import additional configurations.
- Navigate to the `~Documents/fmCheckMate/xml/yEd/fmFieldDependencyGraph` Folder
- Load the latest `FDG_yEdPropertyMap*.cnfx` file.
- Press `[Ok]` to exit

<span style="font-size:90px;">🆗</span>

**👌 OK, we are finally ready to go!**







## Disclaimer

Before you jump into fmGraphIt you should understand its limits:

fmGraphIt's Field dependency graphs are not rocket science - it's not even always right - but it is just about as quick an overview of field structure as you can get in a few clicks without having to create a DDR!

The problem is that since the FileMaker clipboard only contains field calculations as a string, the calculation must be parsed. Since I am no rocket scientist, that means fmGraphIt builds its list of field dependencies by just looking (relatively unintelligently) for occurrences of the field names in the calculations.

Sometimes fmGraphIt gets it wrong, for example fmGraphIt ignores relationships, so if a referenced field in a *related* table has the same name as a field in the current table, fmGraphIt will incorrectly consider this as a reference to a field in the current table.

See 'How fmGraphIt works' to get a better understanding of its limits.

## Getting Started

Once you're set up, you can transform your fields into a stunning diagramme with just a few clicks

1. Copy the (important) fields of a table
2. Convert to XML with fmCheckMate
3. Transform to a graphml Field Dependency Graph
4. Open it in your favourite Graphing Tool - yEd - to display the graph

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

## Learn the Meaning of the shapes, colours and codes

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