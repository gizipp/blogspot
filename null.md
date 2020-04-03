---
layout: archive
title: '/null'
desc: "Sebuah arsip null, ialah kumpulan tempat mengaduh, menuduh, mengeluh atau sedikit banyak sebaliknya dari yang menjadi kebenaran."
permalink: /null/
---

<section class="site-archive">
  <div class="home-group">
    {% for post in site.categories.null %}
      <div class="archive-list">
        <div class="archive-title">
          &bull;<a href="{{ post.url }}">
          {% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}
          </a>
        </div>
        <div class="archive-date"><a href="/{{ post.category }}">\{{ post.category }} </a> {{ post.date | date: "%d-%m-%Y" }}</div>
      </div>
    {% endfor %}
  </div>
</section>
