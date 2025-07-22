---
title: fmIDE 'Name That Thing' API
strapline: Just name it to get to it
parent: fmIDE
nav_order: 0100
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

The fmIDE 'Name that Thing' API is the way to get to your things in FileMaker. Tell [fmIDE] what thing you want, and, presto, you get taken to it.

You want to see script `Hello World`?

Just name it:

```url
fmp://$/MyFile?script=fmIDE&$script_name=Hello%20World
``` 

```
Perform Script [ by Name: ”fmIDE” ; Parameter: "$script_name=Hello%20World" ]
```

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmIDE]: fmide.html
