---
title: News
strapline: News for fmWorkMate and MrWatson's Tools
parent: fmWorkMate.com
nav_order: 1000
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

## {{page.title}}

{{page.strapline}}

Read the blog on [mrwatson.de](https://www.mrwatson.de) to keep up to date.

![GitHub](/assets/images/github-mark.png){: .float-front-right .w-64}

### MrWatson's GitHub Ticker

{% capture github %}

<div 
  data-rss-feed="https://github.com/mrwatson-de.atom"
  data-rss-max="10"
  data-rss-link-titles="false"
  data-rss-title-wrapper="h4"
></div>

{% endcapture %}<section class="fullwidth">{{ github | markdownify }}</section>

<script src="https://cdn.jsdelivr.net/gh/55sketch/simple-rss/simple-rss.js"></script>
