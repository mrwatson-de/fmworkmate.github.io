---
title: fmIDE
strapline: A FileMaker Integrated Development Environment
parent: Integration Tools
nav_order: 200
layout: default
github_repo: https://github.com/fmIDE/fmIDE
github_latest: https://github.com/fmIDE/fmIDE/releases/latest
---
[![Get me on Github](/assets/images/get-me-on-github.png){: .mrw-github-corner}]({{page.github_latest}})

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmIDE, the successor to [fmScriptWorkspace], not only gives you direct access to the ScriptWorkspace, but opens up the entirety of the FileMaker development environment - via the fmIDE Name That Thing API - plus fmIDE packs a [powerful action interpreter](https://github.com/fmIDE/fmIDE/wiki/fmIDE-Action-Scripts) for *dynamic scripting* - also, to some extent, within the developer environment.

![fmIDE Name that Thing API](/assets/images/fmide-name-that-thing-a-p-i-256.png){: .float-front-right .mt--16 .w-128}

## The fmIDE Name That Thing API

…opens up the entirety of the FileMaker development environment…

…and, like a rainbow, opens up your heart…

![fmIDE Name that Thing API](/assets/images/fmide-name-that-thing-api-rainbow.jpg)

## Just try it

section under construction! {: .under-construction}

Files that already sport fmIDE deep linking are ready to experience, so download the demo file and give it a spin!

- Download the example file MyFile.fmp12
- Open MyFile.fmp12 in your newest version of FileMaker Pro
- Try clicking one of these links…
  - Open Script `Hello World` 🙈
    - [fmp://$/MyFile?script=fmIDE&$script_name=Hello%20World](fmp://$/MyFile?script=fmIDE&$script_name=Hello%20World)
  - Open Script `Hello World` at step 4 🙈
    - [fmp://$/MyFile?script=fmIDE&$script_name=Hello%20World&$script_step_number=4](fmp://$/MyFile?script=fmIDE&$script_name=Hello%20World&$script_step_number=4)
  - Open layout with internal id 14
    - [fmp://$/MyFile?script=fmIDE&$layout_id=14](fmp://$/MyFile?script=fmIDE&$layout_id=14)
  - Open Custom Function `_Format_Text_` 🙈⚙️
    - [fmp://$/MyFile?script=fmIDE&$custom_function_name=_Format_Text](fmp://$/MyFile?script=fmIDE&$custom_function_name=_Format_Text)
  - Open Theme `MrW`⚙️
    - [fmp://$/MyFile?script=fmIDE&$theme_name=MrW](fmp://$/MyFile?script=fmIDE&$theme_name=MrW)

🙈
: Actions marked with the monkey need the MBS Plugin to work.

⚙️
: Actions marked with the gear can get you to exactly where you want to go in the FileMaker dialog in one extra keypress IFF you install and use the fmIDE Retype Keyboard Buffer Service to retype the name of the thing you are looking for.

## Basic Installation

The basic installation process is simple, just…

1. Paste the fmIDE Module into your main solution file
2. If necessary, tweak it to account for your strange table / 'base layout' naming conventions
3. Copy & paste the tweaked fmIDE Module to all other files in your solution
4. Grant full access users the privilege to accept fmpurls - extended privilege `fmurlscript`

…and you are ready to go!

For further details read the [full installation instructions](https://github.com/fmide/fmide/wiki/About-fmIDE-Installation-and-Setup) on the [fmIDE Wiki](https://github.com/fmide/fmide/wiki).

![GitHub Icon](/assets/images/github.png){: .float-front-right .mt-16 .h-64}

## fmIDE on GitHub

fmIDE is well documented on the [fmIDE Wiki](https://github.com/fmIDE/fmIDE/wiki), and you can [find the latest version](https://github.com/fmIDE/fmIDE/releases/latest) of fmIDE on the [fmIDE GitHub Repository](https://github.com/fmIDE/fmIDE).

{: .mrw-orange-bg}
**Note:** fmIDE has its own separate repository on [GitHub] under the [fmIDE GitHub Repository](https://github.com/fmIDE/fmIDE).

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmScriptWorkspace]: fmscriptworkspace.html
