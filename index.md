---
title: fmWorkMate.com
strapline: Makes FileMaker work
nav_order: 2
layout: default
---
{: .mrw-schwarz-bg}
This site is a 🚧 WORK IN PROGRESS 🚧

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{% capture welcome %}

[![mrwatson.de](made-by-mrwatson-de.png){: .float-front-right .w-128}](https://mrwatson.de)

Welcome to [fmWorkMate.com](https://fmWorkMate.com), the home of [fmWorkMate] and [MrWatson's Tools](mrwatsons-tools.html) for FileMaker developers.

[Made with love by one FileMaker Developer](made-by-mrwatson-de.html) for a whole community of FileMaker developers.
{% endcapture %}<section class="fullwidth mrw-gold-bg">{{ welcome | markdownify }}</section>

{% capture tldr %}

## TL;DR

[fmWorkMate](fmworkmate.html) is cool ; it will make you more productive ; it will [make your FileMaker coding-life more <span class="rainbow">COLOURFUL</span>](fmsyntaxcolorizer.html)

{: .float-front-right .w-25pc}
![Jump Start your FileMaker Experience](jump-start.png)

{: .float-left .w-25pc}
[![GitHub](/assets/images/github-mark.png)](https://github.com/mrwatson-de/fmWorkMate)

{: .text-center }
[Download the latest release](https://github.com/mrwatson-de/fmWorkMate/releases/latest)
from [@mrwatson-de](https://github.com/mrwatson-de)'s\\
[fmWorkMate Repository](https://github.com/mrwatson-de/fmWorkMate) 
on [GitHub](https://github.com/mrwatson-de/fmWorkMate)

{: .text-3xl .text-center .rainbow .text-bold .text-ARMTB}
 (-: NOW :-)

{: .text-center }
and [Jump Start your FileMaker Experience](jump-start.html)

{% endcapture %}<section class="fullwidth">{{ tldr | markdownify }}</section>

{% capture solutions_to_problems %}

## A Toolbox for FileMaker Developers

[![fmWorkMate Toolbox Screenshot](/assets/images/fmworkmate-toolbox-screenshot.png)](https://github.com/mrwatson-de/fmWorkMate){: .float-front-right .w-20pc}

MrWatson's fmWorkMate is a toolbox of free goodies for FileMaker developers.

[![FileMaker Pro](filemaker-pro.png)](filemaker.html)

FileMaker! You do use FileMaker, don't you? We *all* use [FileMaker](filemaker.html)!

## Solutions to your Daily Problems

MrWatson's tools deliver you all kinds of [Solutions to your Daily Problems](solutions-to-daily-problems.html) in FileMaker.

{% endcapture %}<section class="fullwidth mrw-green-bg">{{ solutions_to_problems | markdownify }}</section>

{% capture deep_integration %}

## Deep Integration into the FileMaker GUI

Power at your fingertips.

Don't console yourself with the limited functionality that the FileMaker client offers you.

![fmAutoMate](fmautomate.png){: .clear .float-front-right .w-32}

The functions you want where you want them - at your fingertips.

Install [MrWatson's Integration Tools](integration-tools.html) and get turbo-power at your fingertips - directly within the FileMaker GUI!

{% endcapture %}<section class="fullwidth mrw-orange-bg">{{ deep_integration | markdownify }}</section>

{% capture fmide %}

![fmIDE](fmide.png){: .float-front-right .w-192}

## fmIDE

At the heart of MrWatson's Integration Tools is [fmIDE](fmide.html) - the FileMaker Integrated Development Environment - a simple script module that together with the MBS plugin puts your code at your command.

Grab your code by the horns! You want it? Just [name it](fmide-name-that-thing-api.html) and you get it!

{% endcapture %}<section class="fullwidth fmide-bg">{{ fmide | markdownify }}</section>

{% capture stay_in_the_loop %}

![Stay in the Loop](/assets/images/stay-in-the-loop.png){: .float-front-right .w-192}

## Stay in the Loop

Don't miss out!

Keep on top of the latest developments in MrWatson's Tools on the [News](news.html) page.

[Sign up for MrWatson's Irregular Newsletter](https://buttondown.com/mrwatson-de)

Get the latest from mrwatson-de on GitHub.

{% endcapture %}<section class="fullwidth mrw-schwarz-bg">{{ stay_in_the_loop | markdownify }}</section>

{% comment %}mrwMarkdownLinks{% endcomment %}
[FileMaker]: filemaker.html
[fmIDE]: fmide.html
[fmWorkMate]: fmworkmate.html
[mrwatson.de]: mrwatson.de
