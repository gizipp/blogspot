---
layout: archive
title: Log
permalink: /log/
---
<section>
  {% for post in site.categories.log %}
    <div class="archive-list">
      <div class="archive-title">
        <a href="{{ post.url }}">
        {% if post.shorttitle %}{{post.shorttitle}}{% else %}{{post.title}}{% endif %}
        </a>
      </div>
      <div class="archive-date"><a href="/{{ post.category }}">\{{ post.category }} </a> {{ post.date | date: "%d-%m-%Y" }}</div>
    </div>
  {% endfor %}
</section>
