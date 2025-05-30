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

![Plug Gaps](/assets/images/plug-gaps.png){: .float-front-right .w-64 .mt-16}

## Plug gaps

{: .mrw-gold-bg}

The tools plug gaps in FileMaker functionality

🤒 Medicine for where it hurts!

- While FileMaker Pro [logs some pasting errors](did-that-just-break.html), **in the most complicated and error-prone area of FileMaker - layouts - paste errors are not logged at all!**
  - [Layout Analysis with fmCheckMate](layout-analysis-with-fmcheckmate) is designed specifically to plug that hole!
- While FileMaker does not (yet) support **deep linking** into the FileMaker GUI
  - [fmIDE](fmide.html) allows you to get where you want *fast*.
- FileMaker's Assisted Install file can only go so far in setting up your FileMaker environment
  - [fmSetupAssistant](fmsetupassistant.html) goes the whole way and can not only setup your FileMaker settings, but also some operating system settings too.

![Work Together](/assets/images/work-together.png){: .float-front-right .h-64 .mt-16}

## Work Together

{: .mrw-blue-bg}

MrWatson's Tools are designed to work together

Here are some examples:

- When you use fmTextDiff to compare FileMaker code, fmTextDiff uses fmCheckMate to transform the code into the best format to recognise the differences
  - You can even choose to automatically perform a conversion on one of the files using mTextConverter
- In fmTextMultiplier entering `1..10` in the replacement field will automatically fire up fmTextSeries to create a series to multiply.
- In fmCheckMate
  - entering multiple lines in the replacement field will automatically switch to use fmTextMultiplier to multiply the code.
  - entering multiple lines in both the find and replacement fields will automatically switch to use fmTextConverter to convert the code.
- As evident from the [Case Study Backporting an e-Invoice Solution for GBS GmbH](case-study-backporting-e-invoice-solution-gbs.html).

## Work Consistently

{: .mrw-schwarz-bg}

MrWatson's Tools aim to be consistent

- have [common navigation](navigation-menus-keys.html)
- speak a common language
- have a (kind of geeky) look and feel
