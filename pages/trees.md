---
title: Trees
layout: about
permalink: /trees/
---

{% assign trees = site.data.ghana_trees %}

# Term Trees

Explore the relationship of instruments and dance styles by viewing the following trees:

<div class="row about-narrowed-content">
{% for t in trees %}
<div class="col-md-4 text-center">
<a class="btn btn-secondary m-4" role="button" href="{{ '/trees/' | append: t.slug | append: '.html' | relative_url }}">{{ t.title }} {{ t.type | capitalize }} Tree</a>
</div>
{% endfor %}
</div>
