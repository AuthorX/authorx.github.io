---
author_profile: true
title: Welcome!
---

I'm Dana Callista Lexa, also known on some platforms as @authorx. I like making things, and collaborating in making things, like podcasts, games, and other silly projects. Here are some of the things I've made that I'm proud of:

{% assign ordered_collections = site.collections | where_exp: "item","item.description" | sort: "order" %}
{% for collection in ordered_collections %}
<h1><a href="/{{ collection.label }}">{{ collection.description }}</a> such as:</h1>
{%- assign post = site.categories[collection.label] | first -%}
{%- comment -%}{%- include archive-single.html type=include.type -%}{%- endcomment -%}

<div class="insert">
<h2>
  {%- if post.link -%}
  <a href="{{ post.link }}">{{ post.title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
  {%- else -%}
  <a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a>
  {%- endif -%}
</h2>
  {% if post.excerpt %}<p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>{% endif %}
</div>

{% endfor %}