---
title: A System of Integrated Tools
strapline: 
parent: MrWatson's Tools
nav_order: 0300
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

Developed over [many years](the-history-of-mrwatsons-tools.html) to [solve real-world problems](solutions-to-daily-problems.html), MrWatson's tools have come to cover a wide range of tasks and problems that I and many other FileMaker developers encounter regularly during their daily routine.

![Problems Solved](/assets/images/problems-solved.png){: .float-front-right .w-64 .mt-16}

## Solve Problems

{: .mrw-green-bg}

The tools solve problems at all stages of the development process

- during setup of a FileMaker workplace computer
- throughout all aspects of the development process
- when analysing and debugging databases
- during deployment and patching
- with integrating documentation

See [Solutions to your Daily Problems](solutions-to-daily-problems.html) for more details.

![Plug Gaps](/assets/images/plug-gaps.png){: .float-front-right .w-64 .mt-16}

## Plug Gaps

{: .mrw-gold-bg}

The tools plug gaps in FileMaker functionality

🤒 Medicine for where it hurts!

### Gaps in Debugging Tools

- While FileMaker Pro [logs some pasting errors](did-that-just-break.html),
  - the `import.log` file is hard to digest
    - [fmLogAnalyser] brings the `import.log`file  to life
- in the most complicated and error-prone area of FileMaker - layouts - paste errors are not logged at all!
  - [Layout Analysis with fmCheckMate](layout-analysis-with-fmcheckmate) is designed specifically to plug that hole!
- Similarly fmCheckMate offers an analysis of Custom Functions to check for breakages there too.

See [Did that just Break] for more details.

### Gaps in the Integrated Development Environment

- While FileMaker does not (yet) support **deep linking** into the FileMaker GUI
  - [fmIDE] allows you to get where you want *fast*.

### Gaps in Setup Tooling

- FileMaker's Assisted Install file can only go so far in setting up your FileMaker environment
  - [fmSetupAssistant] goes the whole way and can not only setup your FileMaker settings, but also some operating system settings too.

![Work Together](/assets/images/work-together.png){: .float-front-right .h-64 .mt-16}

## Work Together

{: .mrw-blue-bg}

MrWatson's Tools are designed to work together

Here are some examples:

### fmTextDiff, fmCheckMate, fmCheckMate-XSLT and fmTextConverter

- When you use [fmTextDiff] to compare FileMaker code, fmTextDiff uses [fmCheckMate] & the [fmCheckMate-XSLT] Library to transform the code into the best format to recognise the differences
  - You can even choose to automatically perform a conversion on one of the files using [fmTextConverter]

### fmTextMultiplier and fmTextSeries

- In [fmTextMultiplier] entering `MyField 1..10` in the replacement field will automatically fire up [fmTextSeries] to create a series `MyField 1`, `MyField 2`, ..`MyField 10` to multiply by.

### fmCheckMate, fmTextMultiplier & fmTextConverter

- In [fmCheckMate]
  - entering multiple lines in the replacement field will automatically switch to use [fmTextMultiplier] to multiply the code.
  - entering multiple lines in both the find and replacement fields will automatically switch to use [fmTextConverter] to convert the code.

### …and more

Check out the Case Study [Backporting an e-Invoice Solution for GBS GmbH](case-study-backporting-e-invoice-solution-gbs.html) for an insight how MrWatson's Tools work beautifully together when porting or patching code to deplyed solutions.

![Work Consistently](/assets/images/work-consistently.png){: .float-front-right .h-64 .mt-16 .mr-2}

## Work Consistently

{: .mrw-schwarz-bg}

MrWatson's Tools aim to be consistent

They

- have [common navigation, menus and Keyboard shortcuts](navigation-menus-keys.html)
- have a [common (kind of geeky) look and feel](the-mrwatson-de-logo.html)
- speak a [common language](killer-keyboard-mode.html)

{% comment %}mrwMarkdownLinks{% endcomment %}
[Did that just Break]: did-that-just-break.html
[fmCheckMate]: fmcheckmate.html
[fmCheckMate-XSLT]: fmcheckmate-xslt.html
[fmIDE]: fmide.html
[fmLogAnalyser]: fmloganalyser.html
[fmSetupAssistant]: fmsetupassistant.html
[fmTextConverter]: fmtextconverter.html
[fmTextDiff]: fmtextdiff.html
[fmTextMultiplier]: fmtextmultiplier.html
[fmTextSeries]: fmtextseries.html
