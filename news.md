---
title: News
strapline: News for fmWorkMate and MrWatson's Tools
parent: fmWorkMate.com
nav_order: 1000
layout: default
stylesheets:
- https://unpkg.com/github-calendar@latest/dist/github-calendar-responsive.css
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{: .mrw-gold-bg}

Read the latest on MrWatson's blog on [mrwatson.de](https://www.mrwatson.de) to keep up to date.

## MrWatson's Irregular Newsletter

Check out the [irregular newsletter archives](https://buttondown.com/mrwatson-de/archive/).

## MrWatson's GitHub Ticker

[![GitHub](/assets/images/github-mark.png)](https://github.com/mrwatson-de.atom){: .float-front-right .w-32}

Follow [@mrwatson-de on GitHub](https://github.com/mrwatson-de/#:~:text=Russell%20Watson) to keep up to date with the latest changes.

<!-- 
 ! ###############
 ! GitHub Calendar.
 ! ###############
 !-->
 
<script
  src="https://unpkg.com/github-calendar@latest/dist/github-calendar.min.js"
></script>

<div class="fullwidth white-bg">
<div class="calendar">
    <!-- Loading stuff -->
    Loading the data just for you.
</div>
</div>

<script>
  GitHubCalendar(".calendar", "mrwatson-de", { responsive: false, global_stats: false, tooltips: true });
</script>

{% capture github_feed %}

<div 
  data-rss-feed="https://github.com/mrwatson-de.atom"
  data-rss-max="10"
  data-rss-link-titles="false"
  data-rss-title-wrapper="h4"
></div>

{% endcapture %}<section class="fullwidth">{{ github_feed | markdownify }}</section>

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
