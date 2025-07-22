---
title: How fmGraphIt works
strapline: Under the Hood
parent: fmGraphIt
nav_order: 0200
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

[fmGraphIt] is a tool that provides a quick overview of field dependencies in FileMaker databases. It uses a combination of XSLT transformations, graphml files, and the yEd graphing tool to visualize these dependencies.

1. Copy fields
2. Convert to XML in fmCheckMate
3. Perform XSLT transformation
4. Graphml file
5. yEd graphing tool


## The XSLT

In fmCheckMate the `Analyse > Fields > Create field dependencies graph advanced` XSLT transformation processes the copied fields into a graph, that is a _set of nodes and edges_, where the nodes represent fields, and the edges represent dependencies between those fields - or rather represent the data flow from one field to another.

(Details to come)


A graphml file is created, and fmCheckmate is setup to save the file to the fmCheckMate folder in your Documents folder, and open it. The file opens with the default app for graphml files, which hopefully, is yEd.

## The graphml File

Graphml is a standard format for representing graphs.

It contains the nodes and edges of the graph plus embedded data.

The fmGraphIt graphml file

- represents a directed graph of the data flow (edges) between fields (nodes).
- conains _no_ layouting information. The layouting is left purely to the yEd Graphing Tool.
- adds field meta data to the (field) nodes.

Here is an extract of a graphml file

```xml
<?xml version="1.0" encoding="UTF-8"?>
<graphml xmlns="http://graphml.graphdrawing.org/xmlns">
  :
  <graph edgedefault="directed" id="G">
    :
    <!-- NODES -->
    :
    <node id="F832">
      <data key="d10">_PK_Kommunikation (T-xo)</data>
      <data key="d11">Input Field</data>
      <data key="d12">Single Index</data>
      <data key="d13">AutoIndex</data>
      <data key="d14">Text</data>
      <data key="d15">Normal</data>
      <data key="d16">_PK_Kommunikation (T-xo)</data>
      <data key="d17">Serial</data>
      <data key="d18">1</data>
    </node>
    :
    <!-- EDGES -->
    <edge id="F859F859" source="F859" target="F859"/>
    <edge id="F859F842" source="F859" target="F842"/>
    <edge id="F859F846" source="F859" target="F846"/>
    :
  </graph>
</xml>
```

### Structure of the data

fmGraphIt defines a number of data elements in the graphml file to describe fields:

`Label`
: the name of the field and metadata, e.g. `_PK_Kommunikation (T-xo)`

`Node Type`
: the type of field: `Output Field`, `Initialized Field`, `Input Field`, `Automatic Field`, `Calculated Field`, `Summary Number Field`, `Summary Text Field`.

`Storage`
: the type of storage: `Stored`, `Single Index`, `Double Index`, `Global`, `Unstored`, `Summary`

`AutoIndex`
: whether auto indexing is enabled: `Locked` or `AutoIndex`

`Data Type`
: the type of data stored in the field, e.g. `Text`, `Number`, `Date`, etc.

`Field Type`
: the type of the field, e.g. `Input Field`, `Calculation`, `Summary`, etc.

`Tooltip`
: the text of the tooltip, including the field name, metadata, and calculation

`Calc Type`
: the type of calculation: `Summary`, `Calculated`, `Lookup`, `Serial`, `AutoEnter`, `Data`, `Value`, ``

`Calc Weight`
: an attempt to measure the complexity of the calculation, based on the number of functions used in the calculation. See [below](#calculation-weights) for more details.

### Node XML

The raw XML of a node looks something like this

```xml
    <node id="F832">
      <data key="d10">_PK_Kommunikation (T-xo)</data>
      <data key="d11">Input Field</data>
      <data key="d12">Single Index</data>
      <data key="d13">AutoIndex</data>
      <data key="d14">Text</data>
      <data key="d15">Normal</data>
      <data key="d16">_PK_Kommunikation (T-xo)</data>
      <data key="d17">Serial</data>
      <data key="d18">1</data>
    </node>
```

The data keys `d10`-`d18` reference the data elements described above: `d10` = `Label`, `d11` = `Node Type`, … `d18` = `Calc Weight`

### Edge XML

Here are three edges from the example file:

```xml
    <!-- EDGES -->
    <edge id="F859F859" source="F859" target="F859"/>
    <edge id="F859F842" source="F859" target="F842"/>
    <edge id="F859F846" source="F859" target="F846"/>
```

Edges are defined simply as `<edge id="F859F842" source="F859" target="F842"/>`, where the `source` and `target` attributes reference the nodes/fields by their IDs. (For simplicity fmGraphIt constructs the edge `id` simply by concatenating the source and target node IDs.)

The above three edges thus declare that field `F859` (field with internal ID 859)…

- references itself (via 'Self' or by name)
- feeds data into/is referenced from field `F842`
- feeds data into/is referenced from field `F846`. 

## The yEd Property Mapper

The yEd Property Mapper maps the metadata in the graphml file to the visual properties of the nodes and edges in the yEd graph.

## Layouting in yEd

Once the graph has been opened and mapped, the pile of overlapping nodes can be arranged in a meaningful way.

yEd provides various layout strategies to arrange the nodes and edges in a meaningful way. For field dependency graphs, a hierarchal layout is often the best choice - at least for relatively small graphs.

## Calculation weights

The calculation weight is a measure of the complexity of the calculation, based on the number of functions used in the calculation. It is calculated by counting the kind of functions used in the calculation and assigning a weight to each function.

| **Weight** | **Field Type / Condition**                     | **Description**                                              |
| ---------: | ---------------------------------------------- | ------------------------------------------------------------ |
|      **1** | Normal field                                   | Default minimal weight                                       |
|      **2** | AutoEnter: Data or Value from last record      | A field with a simple auto-enter data or previous value      |
|      **4** | Calculation with no related fields             | A calculation using only local fields                        |
|      **5** | Calculation with related fields                | A calculation referencing other tables (but no Sum/List)     |
|     **10** | Calculation with **Sum(related fields)**       | A cross-table calculation performing a numeric aggregation   |
|     **12** | Summary (numeric)                              | A summary field returning numerical values                   |
|     **14** | Calculation with **List(related fields)**      | A text/list aggregation on related records                   |
|     **16** | Summary (text)                                 | A summary field returning text, **heaviest dependency**      |


Note:

- 'Calculations' here refer to both Calculated fields and AutoEnter fields.
- The Calculation weight is a heuristic and likely does not reflect the actual complexity of the calculation.
- This is a very basic but good start, is not yet in use anyhow, and can surely be improved!
- The weight only reflects the calculation type at this level, a more useful Calculation weight would aggregate the weights of all the fields it references (but that would require a more complex algorithm and is not yet implemented).


{% comment %}mrwMarkdownLinks{% endcomment %}
[fmGraphIt]: fmgraphit.html
[fmIDE]: fmide.html
