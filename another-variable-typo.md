---
title: Another Variable Typo!?
strapline: Don't say I didn't tell you! 🤬
parent: Solutions to Daily Problems
nav_order: 300
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{%capture conversation %}
You use variables, right?

> We all use variables!

They're fantastic!

> Yes!
>

Except, of course, when they are not! 🙁

{% endcapture %}<section class="fullwidth mrw-green-bg">{{ conversation | markdownify }}</section>

## The Problem

…is, of course, when you have a typo in a variable name - or have forgotten to define a variable.

> And that is sadly far too easy to do!

FileMaker offers no help here at all.

For example, you might have a script that looks like this:

{: .steps}
```filemaker
Set Variable [ $AttachementNumber ; 1 ]
Set Variable [ $AttachementCount ; Count( Email.Attachments::pk ) ]
Loop
    Exit Loop If [ $AttachementNumber > $AttachementCount ]  
    #  Process attachment

    Set Variable [ $Filename ; GetNthRecord( Email.Attachments::Filename ; $AttachmentNumber) ]

    #  :

    Set Variable [ $AttatchmentNumber ; $AttatchmentNumber + 1 ]
End Loop
```

Can you spot the mistake(s)?

> 🧐 Doh! 🤯

 - but don't worry, you have good friends at hand to help!

## MrWatson's Solution 1: Copy + Paste

My first solution was to simply **always copy and paste variable names**.

> It's not a bad solution - and I still use it today - just watch out for accidentally doubled up `$$` characters when selecting and replacing variable names!

## MBS Plugin Solution: Variable Checking

Then Christian Schmitz started a wonder solution with the MBS Plugin … variable checking!

FIXME IMAGE

MBS clearly flags up undefined variables, so long as you play by 

### The Rules of the Game

{% capture rules %}

- Turn on MBS Plugin's `VariableChecking` Option
  - Watch out for - and catch - all your undefined variables (& typos!)
- ***Always* define your variables**
  - Don't use `Let` to define your variables, use `Set Variable`.
  - If you've never done this before it might seem like an enormous drag and waste of time
    but, **believe me, it is worth it!**
- **Don't use spaces in your variable names**
- If you have long scripts you'll need to increase the number of script lines MBS scans

{% endcapture %}<section class="fullwidth mrw-gold-bg">{{ rules | markdownify }}</section>

### Best Practice Tips

{% capture tips %}

- Use variables to make your code more self descriptive & readable.
- Define your variables at the start of the script
  - Don't use `Let` to define your variables
  - Don't use a custom function to define your variables automatically
- Use a `# @var $variableName` comment to declare variables where MBS can't recognise the definition
  - For example: before an `Insert Calculated Result` script step
- Avoid using `$$` variables throughout scripts
  - Instead read the value into a normal `$variable`, and output the `$$variable` again at the end.
- Avoid re-using variable names for different things in different parts of the script
- Be aware, that in long steps and calculations the step text is truncated, so the MBS Plugin may may miss ome variable references.
{% endcapture %}<section class="fullwidth">{{ tips | markdownify }}</section>

![fmSyntaxColorizer](fmsyntaxcolorizer.png){:.float-front-right .mt-16 .w-64}

## MrWatson's Solution 2: fmSyntaxColorizer

- fmSyntaxColorizer
- and a useful code transformation to change all variable names in a script to be MBS-friendly

## MBS Plugin Solution 2: MBS variable name type ahead

Christian Schmitz won another beer with his fantastic variable type ahead functionality!

Type the start of a variable, and MBS offers you a menu of all variables starting like that.

Neat.
