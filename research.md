---
layout: page
title: Research
permalink: /research/
description: "The Young Lab engineers organisms using synthetic biology and metabolic engineering to create cell factories, biosensors, and tools for studying microbial communities."
---

<nav class="pub-nav pub-nav-orange">
  <a href="#cell-factories">Cell Factories</a>
  <a href="#biosensors">Genetic Circuits and Biosensors</a>
  <a href="#software">AI &amp; -Omics in the Wetlab</a>
  <a href="#part-kits">Part Kits</a>
  <a href="#software-projects">Software Projects</a>
  <a href="#organizations">Organizations</a>
</nav>

<h2 class="research-group-label">Topics</h2>

<div class="research-section" id="cell-factories">
<h2>Cell Factories</h2>
<p>We explore organisms with interesting and desirable biosynthetic capacity and engineer them to produce useful compounds like fuels, medicines, and materials. We treat cells as chemical factories and apply metabolic engineering to rewire biosynthesis — combining gene knockouts, overexpressions, and combinatorial approaches to test many expression configurations in parallel.</p>
{% assign cell_projects = site.projects | where: "theme", "cell-factories" | sort: "title" %}
{% if cell_projects.size > 0 %}
<ul class="project-links">
{% for proj in cell_projects %}
<li><a href="{{ proj.url | relative_url }}">{{ proj.title }}</a></li>
{% endfor %}
</ul>
{% endif %}
</div>

<div class="research-section" id="biosensors">
<div class="pub-section-title">
<h2>Genetic Circuits and Biosensors</h2>
<a href="#" class="back-to-top back-to-top-orange">↑ top</a>
</div>
<p>We are defining the principles of transferring genetic designs across organisms to enable genetic circuits to be constructed across the tree of life. Our approach avoids developing a parts kit for every new species discovered. Biological systems have an incredible capacity to sense and respond to their environment. We are particularly interested in sensing in the soil.</p>
{% assign biosensor_projects = site.projects | where: "theme", "biosensors" | sort: "title" %}
{% if biosensor_projects.size > 0 %}
<ul class="project-links">
{% for proj in biosensor_projects %}
<li><a href="{{ proj.url | relative_url }}">{{ proj.title }}</a></li>
{% endfor %}
</ul>
{% endif %}
</div>

<div class="research-section" id="software">
<div class="pub-section-title">
<h2>AI &amp; -Omics in the Wetlab</h2>
<a href="#" class="back-to-top back-to-top-orange">↑ top</a>
</div>
<p>Synthetic biology is built on the predictable design of biological systems. We develop combined wetlab-computational tools that improve genetic engineering workflows. Primarily, we have shown how genomics and transcriptomics can be used in new ways to identify, troubleshoot, and develop targets for genetic engineering.</p>
{% assign tool_projects = site.projects | where: "theme", "tools" | sort: "title" %}
{% if tool_projects.size > 0 %}
<ul class="project-links">
{% for proj in tool_projects %}
<li><a href="{{ proj.url | relative_url }}">{{ proj.title }}</a></li>
{% endfor %}
</ul>
{% endif %}
</div>

<h2 class="research-group-label">Resources</h2>

<div class="research-section" id="part-kits">
<div class="pub-section-title">
<h2>Part Kits</h2>
<a href="#" class="back-to-top back-to-top-orange">↑ top</a>
</div>
<p>We distribute standardized genetic part kits that enable reproducible synthetic biology across labs and organisms.</p>
<ul class="project-links">
  <li><a href="https://www.addgene.org/kits/young-opencidar/">OpenCidar</a></li>
  <li><a href="https://www.addgene.org/browse/article/28252864/">Xd MoClo</a></li>
  <li>Dh MoClo</li>
</ul>
{% include addgene-widget.html %}
</div>

<div class="research-section" id="software-projects">
<div class="pub-section-title">
<h2>Software Projects</h2>
<a href="#" class="back-to-top back-to-top-orange">↑ top</a>
</div>
<p>We develop and share open-source software tools for synthetic biology design, data analysis, and genetic engineering workflows.</p>
{% assign software_projects = site.projects | where: "theme", "software" | sort: "title" %}
{% if software_projects.size > 0 %}
<ul class="project-links">
{% for proj in software_projects %}
<li><a href="{{ proj.url | relative_url }}">{{ proj.title }}</a></li>
{% endfor %}
</ul>
{% endif %}
</div>

<div class="research-section" id="organizations">
<div class="pub-section-title">
<h2>Organizations</h2>
<a href="#" class="back-to-top back-to-top-orange">↑ top</a>
</div>
<ul class="project-links">
  <li><a href="https://massbiohub.org">BioHub</a></li>
  <li><a href="https://createbiofoundries.org">CREATE Biofoundry</a></li>
</ul>
</div>
