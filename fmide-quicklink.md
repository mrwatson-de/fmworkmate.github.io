---
title: fmIDE QuickLink
strapline: Link to your FileMaker things quick
parent: fmIDE
nav_order: 0100
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmIDE QuickLink is a little helper tool in the [fmIDE] file that helps you quickly build links (fmp urls) to your FileMaker things, and channel the link to the current / desired instance of FileMaker.

fmp URLs are at the heart of fmIDE's Integration concept. Using fmIDE's fmp URLs, you can jump to virtually anything in your FileMaker Devlopment Environment in an instant.

## The Problems

Three problems make them difficult to use

1. They are difficult to construct (particularly URL escaping of names with spaces and special characters)
2. They are difficult to channel to the correct instance of FileMaker (particularly if you have multiple instances of FileMaker on your machine)
3. Some documentatin platforms (like GitHub / Slack) do not support fmp URLs and they get mangled into strange http URLs.

## The Solution

fmIDE QuickLink attempts to solve all three problems 😎

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmIDE]: fmide.html
