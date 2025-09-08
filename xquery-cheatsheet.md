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

AI produced, so no guarantees here!

## XQuery 3.1 BASICS

Comments
: `(: comment :)`

XPath
: `//BaseTable[UUID/@userName="R.Watson"]/@name` `(: // get name of all tables changed by R.Watson :)`

XML
: `<BaseTable name="fmCheckMate" UUID="..." userName="R.Watson"/>`

Strings
: `"hello"` (: → `hello` // double quotes :)
: `'world'` (: → `world` // single quotes :)
: `'hello "world"'` (: → `hello "world"` :)
: `"MrWatson's ""world"""` (: → `MrWatson's "world"` // double up to escape quote:)
: `"MrWatson's &quot;world&quot;"` (: → `MrWatson's "world"` // use character references! :)
: `"no\nbackslash\rescapes&#13; &#34;XQuery&#x22;""` (: → `no\nbackslash\rescapes¶in "XQuery"` :)
: `"hello" || " " || "world"` (: → `hello world` // String concatenation :)

Sequences
: `(1,2,3)` (: → `1 2 3` // sequences are ouput with spaces :)
: `("hello","world")` (: → `hello world` :)
: `((1,2),("hello","world"))` (: → `1 2 hello world` // embedded sequences are flattened! :)
: `(<hello/>,<world/>)` (: → `<hello/><world/>`  // sequences of xml are ouput without spaces :)`
: `(1,("hello"),<xml>world</xml>)` (: → `1 helloworld`  // sequences can be mixed and nested :)
: `(1)=1` (: → `true` // a single value in a sequence (a 'singleton') is equivalent to itself :)

Filter and Range
: `('one','two','three')[2]` (: → `two` // `[n]` = a filter :)
: `1 to 5` (: → `1 2 3 4 5` // range :)
: `(1 to 10)[. mod 2 = 0]` (: → `(2,4,6,8,10)` // filter can be a function - using `.` to ) :)

Let
: `let $hello := "world" return $hello (: → world :)`
: `let $x := 42 return $x*2 (: → 84 :)`
: `let $xml := <value>some</value> return $xml/value (: → some :)`
: `let $hello := "world" return <hello>{$hello}</hello> (: → <hello>world</hello> // use {} inside XML to refer to vars :)`

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

ControlStructures…:
…FLWOR
: `for $i in 1 to 5 let $sq := $i*$i where $sq > 10 order by $sq return $sq` → `(16,25)`
: (**F**or, **L**et, **W**here, **O**rder by, **R**eturn = The only looping structure in XQuery!)

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
: `(1 to 5)! (function($n){$n*2})`

text() vs data()
: `<a>hi<b>yo</b></a>/text()` → "hi"
: `data(<a year="2025">42</a>/@year)` → "2025"

