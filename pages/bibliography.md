---
title: Bibliography
layout: about
permalink: /bibliography.html
---

# Bibliography

Related research and resources:

{% assign bib = site.data.ghana_bibliography %}

<ul>
{% for b in bib %}
<li id="{{ b.anchor }}">{{ b.resource | markdownify }}</li>
{% endfor %}
</ul>