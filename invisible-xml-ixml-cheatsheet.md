---
title: Invisible XML (iXML) Cheatsheet
strapline: Data Just Wants to Be Format-Neutral
parent: Reference
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Wow! Invisible XML is a dream come true!

## Problem

You have some (unstructured) text input:

```text
Russell Watson
```

and you need a structured form of it?

XML:

```xml
<Name>
  <FirstName>Russell</FirstName>
  <LastName>Watson</LastName>
</Name>
```

or JSON?

```json
{
  "Name": {
    "FirstName": "Russell",
    "LastName": "Watson"
  }
}
```

Fed up of string manipulation in FileMaker?

Never quite got the hang of parsers?

## Solution

Invisible XML (iXML) to the rescue!

```ixml
{My first ixml grammar to parse & structure a name}
Name: FirstName, ' ', LastName.
FirstName: letter+.
LastName: letter+.
-letter: ["A"-"Z"] ; ["a"-"z"].
```

Applying this iXML grammar to the input text `Russell Watson` (using an implementation of an ixml parser) produces the desired XML output:

```xml
<Name>
  <FirstName>Russell</FirstName>
  <LastName>Watson</LastName>
</Name> 
```

FIXME LINKS HERE

Here is a cheatsheet to get you started with iXML.

# Invisible XML (iXML) Cheat Sheet

A quick reference guide to the **Invisible XML (iXML)** standard, based on the W3C Community Group Final Report (2023-12-12).

---

## Purpose

Invisible XML allows you to parse non-XML data and transform it into clean XML using a readable grammar.

---

## Basic Grammar Structure

### Grammar Rules

| Syntax                | Meaning                                              |
| --------------------- | ---------------------------------------------------- |
| `rule: expression.`   | Defiition of a rule. The `.` terminator is required. |
| `rule = expression.`  | Alternative delimiter `=`                            |

Each rule defines how to match input.

- The expression defines what to match
- The rule name becomes an element in the output XML
- The first rule is the root element of the output XML
- Rules are case-sensitive


### Expressions

| Syntax      | Meaning                                                  |
| ----------- | -------------------------------------------------------- |
| `'text'`    | Literal string: match the string `text`                  |
| `"A's"`     | Literal string: match the string `A's`                   |
| `["A"-"Z"]` | Character range: match any character from A to B         |
| `[L]`       | Character class: match a character in the unicode class  |
| `rule`      | Reference: Match the named rule                          |
| `A, B`      | Sequence: match A followed by B                          |
| `A; B`      | Choice: match A **or** B                                 |
| `A \| B`    | Choice: match A **or** B                                 |
| `A?`        | Quantifier: match zero or one A   (optional A)           |
| `A*`        | Quantifier: match zero or more As (optional, multiple As)|
| `A+`        | Quantifier: match one or more As  (multiple As)          |
| `A**B`      | Quantifier: match zero or more As, delimited by B        |
| `A++B`      | Quantifier: match one or more As, delimited by B         |
| `(A, B)`    | Group: treat the elements inside the ()s as a group      |
| `(A, B)*`   | Group quantifier: applies to the whole group             |
| `{comment}` | A comment: ignored(*)                                    |
| `{WS}`      | (*) Some special [built-in rules](#built-in-r ules) are hidden in comments |

---

## Markup Control

### Markup vs Non-Markup

Use the `-` prefix to suppress a rule's XML element or supress matched content:

| Syntax             | Meaning                                                   |
| ------------------ | --------------------------------------------------------- |
| `rule: 'A'`        | Normal = markup and output: Output `<rule>A</rule>`       |
| `-rule: 'A'`       | Supress markup: Output `A`                                |
| `rule: -'A'`       | Supress content: Output `<rule></rule>`                   |
| `-rule: -'A', 'B'` | Supress markup **and** content:Output `B`                 |

- Normal rule → produces XML element:

```ixml
word: [L]+.
```→
  
```xml
<word>abc</word>
```

- Non-markup rule → no XML output:

```ixml
-ws: ' '+.
→ whitespace is ignored in output
```

---

## ⚙️ Special Constructs

### Grouping

You can group elements using parantheses

```ixml
rule1, (rule2, rule3)? → optional group
```

For example:

```ixml
GNU-stands-for: "GNU's", (' ', 'Not', ' ', 'Unix!')+.
```

### Character Classes

```ixml
["A"-"Z"] {→ character range}
[L] {→ unicode character class}
```

Combine character ranges using the or syntax:

```ixml
letter: [A-Z]; [a-z]; [0-9].
```

---

## Built-in Rules

| Rule              | Description                    |
| ----------------- | ------------------------------ |
| `{WS}`            | Whitespace: space, tab, CR, LF |
| `{NL}`            | Newline characters             |
| `{Char}`          | Any valid Unicode character    |
| `{NameStartChar}` | Start char for XML names       |
| `{NameChar}`      | Valid char for XML names       |

Use them directly in grammars — no need to redefine.

---

## Trapping errors

If an input matches the grammar, the XML is created, however, if the input **does not match** an error ixml element is output, describing where the error occurred and what was expected:

```xml
<ixml xmlns:ixml="http://invisiblexml.org/NS" ixml:state="failed">
Failure at line 1 column 9
Given ' ' (codepoint 32). Expecting one of:
   [L] {#4: LastName: [L]+.}
Input:
   Russell  Watson
           ^
</ixml>
```

To test for failiure you can check the XPath (FIXME)

```xpath
/ixml:ixml/ixml:state='failed'
```

where ixml="http://invisiblexml.org/NS"
---

## 🚫 What iXML Does Not Include

- No actions or embedded code (unlike YACC)
- No semantic value computation
- Designed purely to transform input into XML

---

## 📖 Further Reading

- [iXML Spec – W3C Final Report](https://www.w3.org/community/reports/ixml/CG-FINAL-ixml-20231212)
- [invisiblexml.org](https://invisiblexml.org)

---

## ✍️ Tips

- Beware ambiguity: ensure your grammar can only match one way.
  - Don't use `?`as well as '*'.
  - the following is ambiguous:

  ```ixml
  name: ["a"-"z"]+, optional-index?.
  -optional-index: [0-9]*.
  ```

- Use non-markup rules (`-rule`) to strip punctuation, whitespace, etc.
- Use `{WS}` for optional spacing between elements.
- Rule names = XML element names. Be consistent and semantic!
