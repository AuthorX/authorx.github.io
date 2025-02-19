---
author_profile: true
title: Welcome!
---

I'm Dana Callista Lexa, also known on some platforms as @authorx. I like making things, and collaborating in making things, like podcasts, games, and other silly projects. Here are some of the things I've made that I'm proud of:
{% assign ordered_collections = site.collections | where: "description" | sort: "order" %}
{% for collection in ordered_collections %}
<h1><a href="{{ collection.label }}">{{ collection.description }}</a></h1>
Such as:
{% assign post = collection.docs | first %}
{% if post.link %}
<a href="{{ post.link }}">{{ title }}</a> <a href="{{ post.url | relative_url }}" rel="permalink"><i class="fas fa-link" aria-hidden="true" title="permalink"></i><span class="sr-only">Permalink</span></a>
{% else %}
<a href="{{ post.url | relative_url }}" rel="permalink">{{ title }}</a>
{% endif %}
{% endfor %}

* [Podcasts](/podcasts)
    * Such as: [SuperIdols! RPG](https://superidolsrpg.wordpress.com/)
* [Games and supplements](/games)
    * Such as: [Motion and Stillness - Two Moons for Realis](https://author-x.itch.io/motion-and-stillness)
* [Code projects](/code)
    * Such as: [Dialogue Blocks for Publii](https://github.com/AuthorX/PubliiDialogueBlocks)