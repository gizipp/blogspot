---
layout: archive
title: '/junkies'
desc: "Sebuah arsip junkis, ialah kumpulan macam-macam ketidakberaturan."
permalink: /junkies/
---
<section class="site-front block">
  <div class="container home-group">
    {% for post in site.categories.junkies %}
        <div class="grid_9"><h3 class="home-list">&nbsp;&bull;&nbsp; <a href="{{ post.url }}">{{ post.title }}</a></h3></div>
        <div class="grid_1">{{ post.category }}</div>
        <div class="grid_2">{{ post.date | date: "%d-%m-%Y" }}</div>
    {% endfor %}
  </div>
</section>