---
layout: page
permalink: /
---

<div class="lead">
  We use genomics, synthetic biology, and metabolic engineering<br>
  to design and build biosensors and cell factories.
</div>


<hr class="palette-rule"/>

## Latest Articles

{% assign pubs = site.data.publications | sort: "year" | reverse | slice: 0, 3 %}
{% for pub in pubs %}
  {% include pub-item.html pub=pub %}
{% endfor %}

<p><a href="{{ '/publications/' | relative_url }}">All publications →</a></p>

<hr class="palette-rule"/>

{% include addgene-widget.html %}