---
title: Glossary
layout: page
permalink: /glossary/
---

# Glossary

{% capture letters %}{% for item in site.data.hjccc_glossary %}{{ item.term | slice: 0 | capitalize }};{% endfor %}{% endcapture %}
{%- assign uniqueLetters = letters | split: ';' | uniq | sort -%}
{%- assign glossary = site.data.hjccc_glossary | sort: "term" -%}

<ul class="list-inline">
{% for letter in uniqueLetters %}
<li class="list-inline-item h2"><a href="#{{ letter }}">{{ letter }}</a></li>
{% endfor %}
</ul>
<hr>

<div>

{% for letter in uniqueLetters %}
<h2 class="pt-4" id="{{ letter }}">{{ letter }}</h2>

<dl id="glossary-list">
{% for item in glossary %}
{%- assign x = item.term | slice: 0 | capitalize -%}
{%- if x == letter -%}
    <dt class="glossary-def">{% if item.subject %}<a href="{{ '/glossary/' | append: item.slug | append: '.html' | relative_url }}">
    {{ item.term }}</a>{% else %}{{ item.term }}{% endif %}</dt> 
    <dd>- {{ item.definition }}</dd>
{%- endif -%}
{%- endfor -%}
</dl>

{%- endfor -%}
</div>
