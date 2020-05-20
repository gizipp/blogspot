---
layout: default
title: Log
permalink: /log/
---
<main>
  {% for post in site.categories.log %}
    <h2>
      <a href="{{ post.url }}">{% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}</a>
    </h2>
  {% endfor %}
</main>
