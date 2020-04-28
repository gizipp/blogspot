---
layout: archive
title: '/junkies'
desc: "Sebuah arsip junkis, ialah kumpulan macam-macam ketidakberaturan."
permalink: /junkies/
---
<section class="site-archive">
  <div class="home-group">
    {% for post in site.categories.junkies %}
      <div class="archive-list">
        <div class="archive-title">
          <a href="{{ post.url }}">
          {% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}
          </a>
        </div>
        <div class="archive-date"><a href="/{{ post.category }}">\{{ post.category }} </a> {{ post.date | date: "%d-%m-%Y" }}</div>
      </div>
    {% endfor %}
  </div>
</section>
