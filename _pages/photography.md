---
layout: page
permalink: /photography/
title: Photography
description: A growing collection of photos from places I've been. Almost all are unedited. A few are even good. 
nav: true
nav_order: 6
horizontal: false
---

<!-- _pages/photography.md -->
<div class="projects">
{% assign sorted_galleries = site.galleries | sort: "importance" %}

{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for gallery in sorted_galleries %}
      {% include galleries.liquid %}
    {% endfor %}
    </div>
  </div>
{% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for gallery in sorted_galleries %}
      {% include galleries.liquid %}
    {% endfor %}
  </div>
{% endif %}
</div>
