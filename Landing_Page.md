---
layout: page
title: An Incomplete History of Research Ethics
tags: home
date: 2021-16-12 09:58
---
# An Incomplete History of Research Ethics
Welcome to _An Incomplete History of Research Ethics_! My name is [Ismael](https://uk.linkedin.com/in/ismaelkherroubi) and I hope you find this site of use.

_An Incomplete History of Research Ethics_ is a free, online resource to discover some of the events that, throughout the very lengthy history of human knowledge, can be drawn on to reflect on the complex nature of modern research ethics.

This site contains a more accessible version of the text on the [Tiki-Toki](https://www.tiki-toki.com/timeline/entry/1753034/A-History-of-Research-Ethics/) platform, which is more dynamic and interactive. This site is also directly linked to [this GitHub repository](https://github.com/Ismael-KG/A-History-of-Research-Ethics), where you are very welcome to contribute! More on contributing later! For now, let's see how to use this site.

## Navigating this site
There are three main parts to all pages on this site:
* The header above has the relevant title of the page you have open, as well as a button related to contributing via GitHub, and a search box.
* The content of the page will reflect the section you are reading. Links in the content and elsewhere will open in the same tab on your browser.
* The menu on the left lists (i) stories by century in a collapsed menu, followed by (ii) story categories, (iii) story tags, and (iv) all the protocols, also collapsed by default. Both of these (stories and protocols) are shared below too, so you can always come back to the Home Page to find what you need!

### Finding stories
Thanks to how we navigate timelines on Tiki-Toki, stories fit into one of four categories, and can relate to up to four tags. You can search for stories based on their tags or categories.

#### Categories
* **Opening Up Knowledge:** These are stories that have helped knowledge become more accessible. In ancient times, temples, libraries and universities helped store and share knowledge. These institutions continue to up to this day, and the recent open science movement has given this notion great momentum.
* **Legislation, Declarations & Frameworks:** Numerous documents and guidelines have been created throughout the ages that have shaped how research is conducted. This has not always been for the better. The stories in this category captures these documents and some of the debates that surround them.
* **Research Tragedies:** These are examples we find in common discussions of the history of research ethics. They are the tragedies that inspire declarations, legislation and frameworks. But, above all, research tragedies help us learn of the complex nature of research and precisely how _not_ to do it.
* **Improving Research:** This category is for a wide-range of stories that - you might realise - don't quite fit in any of the others! Some of these stories have to do with improvements in scientific methodologies, conceptual developments that help us better engage with society, and activist movements that shape research for the better.

#### Tags
* **How We Do Things**: Roughly, stories with this tag have influenced approaches to the conduct of research and the spreading of knowledge;
* **What We Value:** These are stories about the rise of moral and epistemic values throughout the ages, and do not necessarily reflect any present individual's belief system;
* **Science Influencers:** Stories with this tag are mostly about how people, documents and movements from outside science have shaped its conduct and underlying values; and 
* **Bioethics:** Stories that relate with medical research ethics and have had a particularly strong influence on modern research ethics more broadly)

## A Word of Caution
The content of _The Timeline_, as it is at this point in time and as it will develop, requires engaging with sensitive topics. There is a story about the legal foundation for racism in the US's Jim Crow laws, there are mentions of Nazi experimentation in Germany, and there is a story about the rise of racist and ableist pseudoscience in England.

The content is not intended to be technically difficult to read, but it can be distressing. I do not know if this is avoidable, but I don't think it should be avoided. I have kept the "research tragedies" I have listed (very few at the time I write this) from being too detailed. I think this is okay. But it would be wrong to ignore the pernicious ideologies that have oppressed enormous swathes of the human population and shaped research throughout the ages. It is for this reason that I use the label "What We Value" not as the desired values of a virtuous person, but what *we*, *as a society*, have valued during the course of our difficult history.

## Stories
Below are the stories currently captured in _An Incomplete History of Research Ethics_. Many of these are still a work in progress, as indicated in their name (they end with "(WIP)"). You are free to share these in any format, just please attribute them back to this site. If you would like to help shape the stories or even just see a typo that should be fixed, please have a look at the protocols further below.

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

## Protocols
{% include_relative Protocols.md %}

## A brief history of this timeline
This timeline began as a side-project in [mid-September 2021](https://twitter.com/hermeneuticist/status/1441111868039315462?s=20). As I wrote it, I wondered if it was worth sharing, but I was unsure about getting it through a peer-reviewed journal; besides, I didn't think a lengthy text was the most useful way to learn about the history of research ethics. I spent some time looking for sites to host a free timeline and eventually found [Tiki-Toki](https://www.tiki-toki.com/)! I created an account on 16 October 2021 and uploaded (almost) everything I had written!

Since then, I have realised that tracking changes is very hard. I had been using a document on [HackMD](https://hackmd.io) for writing but it got clunky when trying to see how my work was evolving.

So here we are! The latest big changes have been:
* Creating a DOI, 
* Establishing a list of protocols for potential contributors (rather than this being a lonely endeavour of a mad-man) 
* Creating a site that is less visually pleasing but more accessible than Tiki-Toki (this is entirely thanks to [@yochannah](https://github.com/yochannah)'s generous work)

I continue to make tweaks to this repo and creating content for the many stories relevant to research ethics, and encourage you to join in!
