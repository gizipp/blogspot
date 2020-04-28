---
layout: archive
title: IO
permalink: /io/
---
<section class="site-archive">
  <div class="home-group">
    {% for post in site.categories.io %}
      <div class="archive-list">
        <div class="archive-title">
          <a href="{{ post.url }}">
          {%- if post.shorttitle -%}{{ post.shorttitle }}{%- else -%}{{ post.title }}{%- endif -%}
          </a>
        </div>
      </div>
    {% endfor %}
  </div>
</section>
