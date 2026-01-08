---
title: Svelte Cheatsheet
strapline: I love this stuff
parent: Reference
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Svelte is a radical new approach to building user interfaces in HTML + CSS + JS.

It's beautifully simple and incredibly fast.

Svelte means "write less, do more".

Whereas traditional frameworks like React and Vue do the bulk of their work in the browser, Svelte shifts that work into a compile step that happens when you build your app. This means you write components using a familiar syntax, but Svelte compiles them into highly efficient imperative code that directly manipulates the DOM.

## Quick start

- It's good to know some basic HTML, CSS and JavaScript first.
- Get started using the [Svelte tutorial](https://svelte.dev/tutorial/svelte/welcome-to-svelte).
- Experiment and have fun using the [Svelte playground](https://svelte.dev/playground/hello-world?version=5.43.6)

## Comparing Svelte to FileMaker

| **Concept**               | **FileMaker**                           | **Svelte**                                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Product/App/Solution      | Solution = collection of FileMaker files| Svelte App = single compiled html page    |
| Development environment   | FileMaker Pro                           | VS-Code + Vite + Build                    |
| App in development        | Same collection of files                | Multitude of structured files             |
| File contains             | Schema + Layout + Scripts + etc.        | Svelte component / js-module / asset / …  |
| Unit of functionality     | Add-on = Widget + Data + Scripts        | Svelte component = script + html + style  |
|                           | Folder inc. public + internal scripts   | javascript module                         |
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Functional Area**       | **FileMaker**                           | **Svelte**                                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Programming language      | Schema, Context, Calculations, Scripts  | `<script>all comes under script</script>` |
| Calculations              | Calculation Engine                      | `<script>let a=1;</script>`                   |
| Processes                 | Scripts Engine                          | `<script>functions()</script>`            |
| Schema                    | Tables, Fields, Variables               | Svelte Stores, Context, State             |
| Data Structures           | JSON, Repeating fields                  | Objects, Maps, Arrays,…                   |
| Context                   | Layout, …Table, Found Set, Curr. Rec.   | Context, State                            |
| GUI styling               | Themes & styles                         | CSS                                       |
| GUI layouting             | Layout Engine                           | HTML, DOM + Svelte `{refs}` and bindings  |
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Reactivity**            | **FileMaker**                           | **Svelte**                                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Dependency + updating     | Implicit (calcs) + explicit (triggers)  | Svelte Runes                              |
| unstored Calculations     | referenced field automatically updated  | Svelte Runes: `$state(…) & $derived(calc)`|
| stored Calculations       | only horizontal between fields of a rec | `let a = $state(42) to $derived(a+1)`     |
| Scripts                   | Script trigger                          | Svelte Runes: `$state(…) & $effect(proc)` |
|                           |                                         | Alternative method: `$: expression`       |
| GUI                       | See below                               | See below                                 |
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Data Reactivity**       | **FileMaker**                           | **Svelte**                                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Script Variable Def.      | `Set Variable [ $var ; «expr» ]`        | `let var = «expr» ;`                      |
| Calculation Variable Def. | `Let ( var = «expr» ; var )`            | `() => { let var = «expr»; return var; }` |
| Calculation field         | `a, Num ; b, Num ; c, Calc = a+b`       | `let a = $state(1), b =  $state(2), c = $derived(a+b) // 3` |
| Cust. Func.               | `My_cf ( a ; b ) = a+b`                 | `const my_fn (a,b) = ((a,b) = a+b)`       |
|---------------------------|-----------------------------------------|-------------------------------------------|
| **GUI Reactivity**        | **FileMaker**                           | **Svelte**                                |
| Updating GUI data         | Variables don't update GUI automatically| TO DO                                     |
| Updating GUI data         | Field update GUI automatically (mostly) | TO DO                                     |
| Views                     | List, detail, table-views               | Very Flexible                             |
| Positioning things        | Parts, co-ordinates                     | TO DO HTML Grids?                         |
| Expanding things          | Anchors                                 | TO DO HTML Grids?                         |
| Hiding things             | Hide calculation                        | Reactive CSS                              |
| Animating things          | Layout animation only on FM GO          | Everywhere with CSS                       |
|---------------------------|-----------------------------------------|-------------------------------------------|
|---------------------------|-----------------------------------------|-------------------------------------------|
| **GUI Concept**           | **FileMaker**                           | **Svelte**                                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Text**                  | `Some text`                             | `<p>Some text</p>` (HTML)                 |
|---------------------------|-----------------------------------------|-------------------------------------------|
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Layout variable**       | Variables referenced with `<<$$…>>`     | References use curly brace: `{myVar}`     |
| Initial value is shown…   | `Some text with <<$$myVar>>`            | `<script>let myVar = 1</script>`          |
| but GUI does not update   | True for both FileMaker and Svelte      | `<p>Some text with {myVar}</p>`           |
| when the value is changed | Also true for Svelte Form inputs        | `<input value={myVar}/>`                  |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Manual trigger            | Refresh Object [ "myVarObjName" ]       | `<scrip>input.value={myVar}</script>`     |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Reactive output text      | `<<LayoutCalculation>>`                 | `<script>let myVar = $state(1)</script>`  |
|                           | Updates automatically?                  | `<p>Some text with {myVar}</p>`           |
|---------------------------|-----------------------------------------|-------------------------------------------|
|---------------------------|-----------------------------------------|-------------------------------------------|
| **Fields**                | GUI Fields just work out of the box     | Data reactivity can be easily programmed  |
|---------------------------|-----------------------------------------|-------------------------------------------|
| Field with initial value  | No such thing in FileMaker              | `<script>let myField = 1</script>`        |
| …but with no update       | …but see Variable above for similar     | `<input value={myField}/>`                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| output field              | `<<MyField>> ( [ ] browse [ ] find )`   | `<script>let myField = $state(1)</script>`|
| …updates automatically    |                                         | `<input value={myField}/>`                |
|---------------------------|-----------------------------------------|-------------------------------------------|
| input field               | `<<MyField>> ( [x] browse [x] find )`   | `<script>let myField = $state(1)</script>`|
| …updates data automatically |                                       | `<input bind:value={myField}/>`           |
|---------------------------|-----------------------------------------|-------------------------------------------|
| label + field             | `Label: [LayoutField…] (grouped)`       | `<label>Label <input …/></label>` (HTML)  |
|---------------------------|-----------------------------------------|-------------------------------------------|

## Svelte basics

Svelte Components

Component = File = Function = Style + Markup + Logic

Reactivity in Svelte:

- let variable = value // a variable much like a variable in FileMaker (calculation / script)

- `<input value={name}>` // like a merge field / variable reference (triggered by a change in the variable)
- `<input bind:value={name}>` // bind = input field. bind enables writing inputs back to the field (like the FileMaker Edit option for input field)
- Reactive statements: `$: doubled = count * 2`
- Runes: 
  - `$state` marks reactive variables (turns a variable into a field)
  - `$derived` marks derived values (a calculation trigger)
  - `$effect` marks side effects (a script trigger)
  - `$:` marks reactive statements - is the old way - and only reacts to changes in variables used directly (visible) in the statement

Note that the state rune is on the variable's value, not on the variable's name. So you write

```svelte
<script>
let myVar = $state("value");
</script>


<p>{myVar}</p>
```
