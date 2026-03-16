---
title: fmGraphIt
strapline: Connect the dots
parent: More Utilities
nav_order: 0040
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

## The Problem

You've got a table with a lot of fields, you want to understand how they work together, which fields are used in which calculations, and how the data flows through the table.

> How do these fields work together?

I know, that can be quite a time intensive question to answer!

> I'm fed up of trawling though field definitions to understand how fields hang together!

How about a diagramme instead? That'd be worth a thousand clicks?

  ![Trawling Fields](/assets/images/fmgraphit-a-picture-is-worth-a-thousand-words.png)

## The Solution

**fmGraphIt**! A way of visualizing data flow and dependencies between the fields of a FileMaker database table.

Just copy the fields and get the big picture with **fmGraphIt**  in just a few clicks!

For example, here are the fields of the communicaton table for telephone numbers, email addresses, etc. in the advanter ERP system.

[![Example Field Dependency Graph](/assets/images/fmgraphit-example-field-dependency-graph.svg)](/assets/images/fmgraphit-example-field-dependency-graph.svg)

- A picture is worth a thousand words!

{: .mrw-gold-bg}
And an interactive diagramme is worth a thouand beers! 🍻

- Click the image to see it in action!
- Hover on a field to see the calculation and other details

## What is fmGraphIt?

**fmGraphIt** is not a single tool, as such - there is no fmGraphIt file - rather, it is:

- a way of displaying field information in a rich, meaningful way
- a process, starting with an XSLT transformation within the [fmCheckMate-XSLT] library,
- a set of mapping files to implement those display conventions within the yED graphing tool.

## Installing fmGraphIt

To generate a field dependency graph from the field definitions of one table you will need

![fmWorkMate and fmCheckmate](/assets/images/fmworkmate-and-fmcheckmate.png){: .float-front-right .w-128}

<details markdown="1">
<summary>fmGraphIt is part of fmWorkMate and the fmCheckmate-XSLT library. If you already have them, you can skip this step.</summary>

1. [Install and Setup the fmWorkMate toolbox](fmworkmate.html#installation-and-setup) (which includes the [fmCheckMate] tool)

   ![](fmcheckmate-xslt.png){: .float-front-right .w-64}

2. Install MrWatson's [fmCheckMate-XSLT] Library (which includes the graph creation function)

</details>

![](yed.png){: .float-front-right .w-64}

To visualise this field dependency graph you will need a graph visualisation tool.

- The free **yEd** software from **yWorks**

- Download the [latest version of yEd from yWorks](https://www.yworks.com/products/yed)

1. some yEd configuration files for formatting the graph (which are to be found in the xml/yEd folder of The **fmCheckMate-XSLT Library**)

2. Finally, you need

   - A step-by-step guide to installing **fmGraphIt** ( **fmWorkMate**, the  **fmCheckMate-XSLT Library**, and yEd)
   - A tutorial on creating your first Field Dependency Graph
   - A Field Dependency Graph Legend
   - An introduction to yEd

{:.text-3xl .emoji-icon .clear .float-front-right}
🆗

{: .fullwidth .mrw-schwarz-bg}
**👌 OK, we are finally ready to go!**


{: .side-note .float-front-right}
<details markdown="1">
<summary>Disclaimer and Limitations</summary>
**Disclaimer:**

fmGraphIt's field dependency graphs are not rocket science—they're not always perfect—but they provide a quick overview of field structure without needing to create a DDR.

Since the FileMaker clipboard only contains field calculations as a string, the calculation must be parsed. fmGraphIt builds its list of field dependencies by simply (but smartly) searching for occurrences of field names in the calculations.

**Limitations:**

- **False positives:** fmGraphIt might falsely interpret text in the calculation (a comment, relationship name,r function name, etc.) as a field reference, if the text matches.
- **Relationships** are ignored. If a referenced field in a *related* table has the same name as a field in the current table, fmGraphIt may incorrectly consider this as a reference to the current table's field.

See [How fmGraphIt works](how-fmgraphit-works.html) for more details on its limitations.

</details>

## Disclaimer

Before you jump into **fmGraphIt** you should understand its limits.

## Getting Started

Once you're set up, you can transform your fields into a stunning diagramme with just a few clicks

1. Create a graphml file of your fields with [fmCheckMate]
   1. Copy the fields of a table you are interested in
   2. Convert to XML with [fmCheckMate]
   3. Press `[T]` and apply the Transformation `Analyse > Fields > Create field dependencies graph advanced` to create a graphml Field Dependency Graph
      - This saves the `Clipboard.graphml` file to your documents folder, and opens it with the default editor (yEd)
2. Visualise the graph in yEd
   1. The graph is initially displayed in [yEd] as a pile of dots
      - No problem, that's normal, read on.
   2. Apply style to the graph
      - Open the property mapper with `Edit > Properties Mapper…`
      - Apply the standard style
        - Select `FDG: Template = Default (Node)`
        - Click `[Apply]`
      - Click `[OK]`
      - You'l see the dots get shape and colour, but are still all in a pile…
   3. Now apply a layout-strategy (`Hierarchical` is the best layout for showing data flow)
     - Select menu item `Layout`> `Hierarchal` or press <kbd>⌃</kbd><kbd>⌘</kbd><kbd>H</kbd>
     - Check the settings, particularly the `General` and `Edges` settings:

       ![yEd Hierarchic Layout General Settings](/assets/images/yed-hierarchic-layout-general.png){: .w-40pc}![yEd Hierarchic Layout Edge Settings](/assets/images/yed-hierarchic-layout-edges.png){: .w-40pc}

     - Click `[OK]` and watch the graph come to life!

You should see something like the example graph below.

Common issues and tips:

<details markdown="1">
<summary>Layout cramped or oriented?</summary>
 - Try tweaking the layout settings for the best look:
   - `General` > `Orientation`:
     - `Top to Bottom` - recommended (because of the downward pointing triangles), particularly on smaller graphs
     - `Left to Right` - can work better with many fields or long field names
   - `Edges` > `Routing Style`: 
     - `Polyline` - the default, and good for most graphs
     - `Octilinear` - gives the graph a circuit-board look: great for nerds 🤓
 - Alternatively try a different layouting strategry
   - `One-Click Layout` - yEd does its best to find the right layout for your data
   - `Organic` - to discover the complex bits
   - `Circular` - to see the loops
</details>

<details markdown="1">
<summary>Too complex?</summary>

- Over full graphs can be difficult to navigate, so try to simplify the graph by removing some fields
- Copy less fields to the clipboard in the first place
- Remove all fields that have no dependencies (no arrows in or out)
</details>

<details markdown="1">
<summary>Want to focus?</summary>

- Zoom in on a particular area of the graph

  ![yEd Zoom Tools](/assets/images/yed-zoom-tools.png)

  - Select the magnifying glass tool
  - Then select the nodes you want to zoom in on
  - To return to the full view click the zoom out button on the right 
- Select the field you are interested in and study its connections
  - Use the `Context Views` from the `Windows` menu to focus on certain connections
  - `Neighbourhood` - shows the input / output fields around the selected field
  - `Predecessors` - shows the tree of input fields which feed the selected field
  - `Successors` - shows all the output fields of the selected field
</details>

## Example Field Dependency Graph

The diagramme shows the field dependencies, or rather the data flow from the (squarish) input fields at the top to the (triangular) calculated output fields at the bottom.

[![Example Field Dependency Graph](/assets/images/fmgraphit-example-field-dependency-graph.svg)](/assets/images/fmgraphit-example-field-dependency-graph.svg)

### Legend

Here is the legend to the shapes, colours and codes used in the graph:

[![Field Dependency Graph Legend](/assets/images/fmgraphit-field-dependency-graph-legend.svg)](/assets/images/fmgraphit-field-dependency-graph-legend.svg)

(Click the image for a large view)

## fmGraphIt Field Dependency Graph Explained

Here is how to read the graph…

### Field Labels

Each field is labelled with its name and some (cryptic but succinct) metadata:

- `«field-name»` (`«data-type»`-`«storage-type»``«field-type»`)

#### Data Type

{: .side-note .w-40pc}
That's the same letter as the shortcut key for the data type

The data type is indicated by the following codes:

`T`
: Text

`N`
: Number

`D`
: Date

`I`
: Time

`M`
: Timestamp

`R`
: Container

{: .side-note .w-33pc}
Storage is also indicated by the [colour](#colours)

#### Storage Type

Storage is indicated by the following codes

`$`
: **$**-variable (`$-` for script variable and `$$` for global variable)

`g`
: **g**lobal

`s`
: **s**tored

`x`
: inde**x**ed (small x = single index)

`X`
: inde**X**ed (large X = double index)

`u`
: **u**nstored

{: .side-note .w-33pc}
Field type is also indicated by the [shape](#shapes)

#### Field Type

The type of field is indicated by the following codes

`O`
: an initialised **O**utput field (auto enter & _no_ overwrite & _no_ modification)

`o`
: an initialised **o**nce field (auto enter & _no_ overwrite but modifiable)

`f`
: a normal (input) **f**ield (small f = no frills)

`F`
: a **F**ilter **F**ield  (large F = with auto enter & overwrite)

`C`
: a **calculation** field

`S`
: a **s**ummary field

For variables the following codes are used (or rather will be one day):

`-`
: a **$-**script variable

`$`
: a **$$** global variable

### Shapes

{: .side-note .w-33pc}
The pointier the shape, the more complex the [type of field](#field-type).<br>⏺️→⏹️→⏢→▶️→*️⃣

The shape indicates the [field type](#field-type):

- ⏹️ Square shapes are input fields
- ▶️ Triangular shapes are output fields
  - 🔼 Upwards pointing are data source fields (locked + initialised fields, creation date, etc.)
  - 🔽 Downwards pointing are data aggregators (calculation fields)
- ⏢ 'Tweeny' shapes are a bit of both
  - 1/2 ⏹️ + 1/2 ▶️ = 1/2 input + 1/2 output = Auto-Enter fields
- *️⃣ Star shapes are summary fields
- ⏺️ Circle shapes are variables.

See the [Field Depency Graph Legend](#legend) for more details.

{: .side-note .w-40pc}
More colour → more storage<br>lighter → less CPU<br>darker → more CPU

### Colours

The colour indicates the [storage type](#storage-type), and follow these simple guidelines:

See the `Storage vs CPU` part of the legend for more details.

### Top to Bottom Layout Orientation

{: .side-note .w-33pc}
Data flows from top to bottom

The shapes of the fields have been chosen to fit a top-down hierarchy well visually.

- At the top you find `source` and `input` fields`:
  - 🔼 non-modifiable metadata fields ('output' source fields)
  - ⏹️ normal input fields (with/without Auto Enter)
- In the middle you find fields that build on the source + input fields:
  - ⏢ auto-enter fields
  - 🔽 calculation fields
- Towards the bottom you find the deeper 'aggregator' fields:`
  - 🔽 calculation fields
  - *️⃣ summary fields

Note: The arrows show data flow rather than dependency

### Tooltip - Calculation Type

In the calculation in the tooltip, the kind of 'equals sign' used indicates what kind of calculation it is:

`=`
: Calculated field

`:=`
: Autoenter field

`<=`
: Lookup field



<details markdown="1">
<summary>Note: This is a subset of the fmCheckMate Print fields function</summary>

`_ID :+1 7`
: A field with auto-incremented serial number (Auto-Increment)

`active : "1"`
: A field with an auto-enter fixed text (Auto-Data)

`Status := "New"`
: A field with an auto-enter initial calculated value (Auto-Init)

`DateDeparture :== DateArrival+2`
: A field with an auto-enter filter calculated value (Auto-Calc)

`Info :=== "Input: " & Quote(Input)`
: A field with an auto-enter filter calculated value even when inputs empty

`RepIndex = ArrIndex+1`
: A calculated field

`_sTotal =∑: Score`
: A statistic field = Total

`_sCount =N: Options`
: A statistic field = Count

`_sAve =∑/N: Score`
: A statistic field = Average

`_sMin =≤: Score`
: A statistic field = Minimum

`_sMax =≥: Score`
: A statistic field = Maximum

`_StdDev =σ: Score`
: A statistic field = Standard Deviation

`_Frac =½: Score`
: A statistic field = Fraction of Total

`_List =∑¶: Names`
: A statistic field = List of Text

</details>

Enjoy!

MrWatson

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmCheckMate]: fmcheckmate.html
[fmCheckMate-XSLT]: fmcheckmate-xslt.html
[fmWorkMate]: fmworkmate.html
[How fmGraphIt works]: how-fmgraphit-works.html
[yEd]: yed.html
