---
layout: page
title: A History of Research Ethics
tags: home
date: 2021-01-12 10:47
---

## Temporary index:

### Pages that have been migrated to Jekyll format

<div class="trigger">
<ul>

{% comment %} We only want to output Story pages, not any other pages (such as the 404 error page or index page){% endcomment %}  

  {% assign pages = site.pages %}
  {% assign stories = pages | where: "layout", "story"%}


  {% assign sorted = stories | sort: "historical-date.year" | reverse %}


  {% for page in sorted %}
    {% if page.historical-date.bce %}
      <li><a class="page-link" href="{{ page.url | prepend : site.baseurl }}">
        {{page.historical-date.year}}
        BCE:
        {{ page.title }}
      </a></li>
    {% endif %}
  {% endfor %}

    {% comment %} we sort by year, but don't forget we sorted alll BCE dates... backwards!  {% endcomment %}
    {% assign sorted_forwards = sorted | reverse %}

    {% for page in sorted_forwards %}
      {% unless page.historical-date.bce %}
        <li><a class="page-link" href="{{ page.url | prepend : site.baseurl }}">
          {{page.historical-date.year}}
          CE:
          {{ page.title }}
        </a></li>
      {% endunless %}
    {% endfor %}

  </ul>
</div>

{% include_relative README.md %}
