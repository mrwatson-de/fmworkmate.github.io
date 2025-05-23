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

<script>
  (function(){
    const rules = [
      { keyword: 'release',    className: 'mrw-green-bg' },
      { keyword: 'issue',    className: 'mrw-orange-bg'   }
    ];

    const feedContainer = document.querySelector('[data-rss-feed]');
    if (!feedContainer) return;  /* nothing to do if missing */

    function highlightByRules(nodes, rules) {
      nodes.forEach(div => {
        const text = div.textContent.toLowerCase();
        rules.forEach(({ keyword, className }) => {
          if (text.includes(keyword.toLowerCase())) {
            div.classList.add(className);
          } else {
            div.classList.remove(className);
          }
        });
      });
    }

    /* helper to grab the current set of feed-item nodes */
    function getFeedNodes() {
      return feedContainer.querySelectorAll('div.js-feed-item-view');
    }

    /* initial pass */
    highlightByRules(getFeedNodes(), rules);

    /* observer + debounce: re-run highlight after 300ms of no mutations */
    let debounceTimer;
    const observer = new MutationObserver(() => {
      clearTimeout(debounceTimer);
      debounceTimer = setTimeout(() => {
        highlightByRules(getFeedNodes(), rules);
      }, 300);
    });

    observer.observe(feedContainer, {
      childList: true,   /* watch for added/removed direct children */
      subtree:   true    /* …and their descendants */
    });

    /* to stop observing later: observer.disconnect(); */
  })();
</script>
