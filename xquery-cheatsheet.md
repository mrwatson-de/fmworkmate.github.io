---
title: XQuery Cheatsheet
strapline: Lets get up to speed with XQuery!
parent: Reference
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

XQuery is a stunningly powerful language to query and transform structured data XML data or even jSON.

It's a full blown language with variables, functions, control structures, types and modules.

Whereas in FileMaker 'everything is text', in XQuery 'everything is a sequence'.

## XQuery 3.1 BASICS

Comments
: `(: comment :)`

XPath
: `//BaseTable[UUID/@userName="R.Watson"]/@name` // get name of all tables changed by R.Watson

XML
: `<BaseTable name="fmCheckMate" UUID="..." userName="R.Watson"/>`

Strings
: `"hello"` → `hello` // double quotes
: `'world'` → `world` // or single quotes
: `'hello "world"'` → `hello "world"` // use what fits best!
: `"MrWatson's ""world"""` → `MrWatson's "world"` // double up quotes to escape[^1]
: `'MrWatson''s "world"'` → `MrWatson's "world"` // or double up apostrophes[^1]
: `"MrWatson's &quot;world&quot;"` → `MrWatson's "world"` // alternatively use XML character references!
: `'&#10;'`→ LF // literal newline character
: `codepoints-to-string(10)`→ LF // or generate newline character (~Char(10) in FileMaker)
: `"no\nbackslash\rescapes&#13;in &#34;XQuery&#x22;"` → `no\nbackslash\rescapes¶in "XQuery"`
: `"hello" || " " || "world"` → `hello world` // String concatenation operator
: `concat("hello"," ","world")` → `hello world` // String concatenation function

Sequences
: `(1,2,3)` // a sequences is an ordered list of items
: `("hello","world")` // of any type
: `(1,"hello",<xml>world</xml>)` // of mixed types
: `1 to 5` → `(1,2,3,4,5)` // range = sequence of numbers
: `((1,2),("hello"))` → `(1,2,"hello")` // sequences are always flat / flatened!
: `//Book` → `(«Book1»,«Book2»,«Book3»)` // sequences are everywhere in XQuery!
: `(1,2,3)` → `1 2 3` // sequences are ouput with spaces
: `("hello","world")` → `hello world`
: `(<hello/>,<world/>)` → `<hello/><world/>`  // xml sequences are ouput without spaces `
: `(1,("hello"),<xml>world</xml>)` → `1 helloworld` // not the mixed delimiters!
: `(1)=1` → `true` // a single value in a sequence (a 'singleton') is equivalent to itself!

Filters
: `('one','two','three')[2]` → `two` // `[n]` = a simple positional filter (1-based)
: `(1 to 10)[. mod 2 = 0]` → `(2,4,6,8,10)` // filter can be a function (use `.` to reference item)

Types
: `xs:string` `xs:int` `xs:dateTime` `node()` `item()`

Operators…
…Maths
: `+` `-` `*` `div` `idiv` `mod`

…Comparison
: `=` `!=` `<` `>` `<=` `>=`  (value)

…General operators
: `eq` `ne` `lt` `gt`

…Logical operators
: `and` `or` `not()`

…Concatenation ops
: `||` string concat, `,`  sequence concat

…Bang operators
: `(1,2) ! (. * 2)`

…Arrow operators
: `"Hello" => upper-case() => substring(1,3)`

…Set operators
: `union` `intersect` `except`
: Note: these remove duplicates and sort the result!
: `(3,2,1,2) union ()` → `(1,2,3)`

Control Structures…:

…let
: `let $hello := "world" return $hello` → `world`
: `let $x := 42 return $x*2` → `84`
: `let $xml := <value>some</value> return $xml/value` → `some`
: `let $hello := "world" return <hello>{$hello}</hello>` → `<hello>world</hello>` // use `{}` inside XML to refer to vars/switch back to XQuery[^1]

{% capture FLWOR %}
**F** or

**L** et

**W** here

**O** rder by

**R** eturn
{% endcapture %}<section>{{ FLWOR | markdownify }}</section>{: .side-note}

…FLWOR
: `for $i in 1 to 5 let $sq := $i*$i where $sq > 10 order by $sq return $sq` → `(16,25)`

…Conditionals
: `if ($x > 0) then "positive" else "non-positive"`

…Switch
: `switch($day) case "Sat" return "weekend" "Sun" return "weekend" default return "weekday"`

…Typeswitch
: `typeswitch($x) case xs:string return "string" case xs:integer return "integer" default return "other"`
: Note: Typeswitch first becomes really useful with schema-aware XQuery (more expensive licence)

…Mapping
: `(1,2,3) ! (. * 2)` → `(2,4,6)`

…Arrow
: `"Hello World" => substring(1,5) => upper-case()` → `HELLO`

…Predicates
: `(//book)[2]` → second book element
: `(1 to 10)[. mod 2 = 0]` → `(2,4,6,8,10)`
: `("A","B","C","D","E","F","G","H","I")[position() = (1,3,5,9)]` → `(A,C,E,I)`

…Quantifiers
: `some $n in 1 to 10 satisfies $n mod 2 = 0` → `true`
: `every $n in 1 to 10 satisfies $n > 0` → `true`

Try/Catch
: `try { 1 div 0 } catch * { "division by zero" }` → `division by zero`

Built-ins
: `concat()`, `substring()`, `upper-case()`
: `count()`, `empty()`, `distinct-values()`
: `sum()`, `avg()`, `min()`, `max()`

Constructors
: `element()`, `attribute()`, `text()`, `comment()`, `document()`, `processing-instruction()``

Functions
: `declare function local:f($x){$x*$x};`

Modules
: `module namespace m="http://ex";`
: `declare function m:f($x){$x*$x};`
: `import module namespace m="http://ex" at "m.xqm";`

Maps/Arrays
: `map{"a":1,"b":2} => map:get("a")`
: `["x","y"][2]`

Higher-order
: `(1 to 5)! (function($n){$n^2})` → `(1,4,9,16,25)`

text() vs data()
: `<a>hi<b>yo</b></a>/text()` → "hi"
: `data(<a year="2025">42</a>/@year)` → "2025"

## Syntax order

XQuery supports modern (left to right) 'pipeline' syntax with the arrow operator `=>` and bang operator `!`.

This is far more logical and easier to read than the traditional nested function syntax. At least, once you have got used to it.

Traditional (middle-outwards) syntax
: `string-join(distinct-values(("hello","world","hello")),"&#10;")`

Modern (left→ right) Pipeline syntax
: `("hello","world","hello") => distinct-values() => string-join("&#10;")`

# Common Patterns

## List of unique Values

List of Variable names used in a file

```xquery
distinct-values(//Step[@name='Set Variable']/Name)
  => string-join("&#13;")
```

## Sorting

{% capture sorting %}
Sorting in XQuery 3.1 is a bit tricky

- The default sort order is not so useful (unicode codepoint order)
  - You can remedy this by using `declare default collation` (see below)
- The `order by` clause requires a `collation «url»` clause (which is a bit unwieldly)
- moreover it only supports a *static* url and thus is not replaceable by a short variable.
- On the other hand, the `sort` function *does* support dynamic collations.
- Happily this is all fixed in XQuery 4.0! 😃
{% endcapture %}<section>{{ sorting | markdownify }}</section>{: .note}

### Sorted List of Unique Values (in natural order)

Sorted list of Variable names used in a file with a natural (case-insensitive) sort order

```xquery
declare default collation "http://www.w3.org/2005/xpath-functions/collation/html-ascii-case-insensitive";
(
for $name in distinct-values(//Step[@name='Set Variable']/Name)
order by $name
return $name
) => string-join("&#13;")
```

returns

```text
$aardvark
$Apple
$banana
$Cat
$dog
```

### Sorted Unique Values (standard sort order)

- For more natural sorting you need to use a collation

```xquery
for $name in distinct-values(//Step[@name='Set Variable']/Name)
order by $name
return $name
  => string-join("&#13;")
```

returns

```text
$Apple
$Cat
$aardvark
$banana
$dog
```

## List Scripts containing a search term

```xquery
(
let $search := 'Set'
for $script in //Script
let $script_name := $script/data(@name)
where contains($script,$search)
return $script_name
) => string-join('&#10;')
```

## Filter results using RegEx

- the filter function applies a function to each item in the sequence and if the function returns true the item is kept.
- the match function tests a regular expression and returns true if it matches.

List Variable names used in a file, sorted, filtered to only those containing 'Anzahl' or 'count' (case insensitive), but not account.

```xquery
let $regex := '([Aa]nzahl|(C|[^c]c)ount)'  (: regex to match :)
return (
for $name in distinct-values(//Step[@name='Set Variable']/Name)
order by $name
return $name
)
=> filter(matches(?, $regex))  (: keep only matching results :)
=> string-join('&#10;')
```


<hr/>

# XQuery snippets for MrWatson

These are just some XQuery snippets that I'm storing here for now.

## Get distinct script parameter types from SaXML

```xquery
(
for $name in distinct-values(/FMSaveAsXML/Structure/AddAction/StepsForScripts/Script/ObjectList/Step/ParameterValues/Parameter/@type)
order by $name
return $name
) => string-join("&#13;")
```

## Examine script parameters used within a scipt

```xquery
let $script_name := "All script steps and all options",
     $script_parameter_type := "AccountType"
return
(
for $parameter in /FMSaveAsXML/Structure/AddAction/StepsForScripts/Script/ObjectList/Step/ParameterValues/Parameter[@type=$script_parameter_type]
return $parameter
)
```

## Examine elements referencing a (table) name

```xquery
(
for $element in //*
where $element[not( ancestor-or-self::Field) and contains(data(@name),'dress') ]
return $element
)
```

# Footnotes

[^1]: **Double up to escape** is the concept of the day! If you need to embed an xml element that really contains `{}` then you need to **double up to escape** the braces here too: Use `<xml>{{{{"some"\:"json"}}}}</xml>` to encode `<xml>{{"some":"json"}}</xml>` in the output.
