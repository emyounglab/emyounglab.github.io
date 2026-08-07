---
layout: page
title: Publications
permalink: /publications/
description: "Peer-reviewed publications, preprints, reviews, book chapters, and patents from the Young Lab at Worcester Polytechnic Institute."
---

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign total = pubs.size %}

{% assign years = "" | split: "" %}
{% for p in pubs %}
{% unless years contains p.year %}{% assign years = years | push: p.year %}{% endunless %}
{% endfor %}

<nav class="pub-nav">
{% for y in years %}<a href="#year-{{ y }}">{{ y }}</a>{% endfor %}
</nav>

<div class="pub-section">
{% for y in years %}
{% assign count_before = 0 %}
{% for p in pubs %}
{% if p.year > y %}{% assign count_before = count_before | plus: 1 %}{% endif %}
{% endfor %}
<h3 id="year-{{ y }}" class="year-stamp">{{ y }}</h3>
{% assign year_pubs = pubs | where: "year", y %}
{% for pub in year_pubs %}
{% assign pub_num = total | minus: count_before | minus: forloop.index0 %}
{% include pub-item.html pub=pub num=pub_num %}
{% endfor %}
{% endfor %}
</div>
