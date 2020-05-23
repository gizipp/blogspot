---
layout: default
title: GIXIPP
permalink: /gixipp/
---
<main style="font-size: .8em;">
  {% for post in site.categories.gixipp %}
    <h2>
      <a href="{{ post.url }}">{% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}</a>
    </h2>
  {% endfor %}
</main>
