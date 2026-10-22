---
layout: page
title: Tags
permalink: /tags/
---

<h1>Browse PeriodWise Articles by Tag</h1>

<p>Explore articles by menstrual cycle, fertility, ovulation, and reproductive health topics.</p>

{% assign sorted_tags = site.tags | sort %}

{% for tag in sorted_tags %}
  {% assign tag_name = tag | first %}
  {% assign tag_posts = tag | last %}
  {% assign tag_id = tag_name | slugify %} 

  <section class="tag-section">
    <h2 id="{{ tag_id | escape }}">{{ tag_name | escape }}</h2>

    <ul>
      {% for post in tag_posts %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}
