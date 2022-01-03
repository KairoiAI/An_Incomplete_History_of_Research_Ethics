---
layout: default
title: Tag index
show-in-nav: true
---

{% assign rawtags = "" %}
{% for post in site.pages %}
  {% assign ttags = post.tags | join:'|' | append:'|' %}
  {% assign rawtags = rawtags | append:ttags %}
{% endfor %}
{% assign rawtags = rawtags | split:'|' | sort %}

{% assign site.tags = "" %}
{% for tag in rawtags %}
  {% if tag != "" %}
    {% if tags == "" %}
      {% assign tags = tag | split:'|' %}
    {% endif %}
    {% unless tags contains tag %}
      {% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
    {% endunless %}
  {% endif %}
{% endfor %}

{% for tag in tags %}
<li><a class="page-link" href="{{ tag | prepend : site.baseurl }}">

    {{tag}}

  </a></li>
{% endfor %}
