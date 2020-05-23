---
layout: archive
title: '/null'
desc: "Sebuah arsip null, ialah kumpulan tempat mengaduh, menuduh, mengeluh atau sedikit banyak sebaliknya dari yang menjadi kebenaran."
permalink: /null/
---

<main style="font-size: .8em;">
  {% for post in site.categories.null %}
    <h2>
      <a href="{{ post.url }}">{% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}</a>
    </h2>
  {% endfor %}
</main>
