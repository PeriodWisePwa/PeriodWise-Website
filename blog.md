---
layout: default
title: Blog
permalink: /blog/
---

<div class="main-content">

  <h1>PeriodWise Blog</h1>

  <p>
    Practical, easy-to-understand information about menstrual cycles,
    fertility, ovulation, period tracking, and reproductive health.
  </p>

  <div class="posts-list">
    {% for post in site.posts %}
      <article class="post-preview">
        <h2>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>

        <p class="post-meta">
          {{ post.date | date: "%B %-d, %Y" }}
        </p>

        {% if post.description %}
          <p>{{ post.description }}</p>
        {% else %}
          <p>{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
        {% endif %}

        <p>
          <a href="{{ post.url | relative_url }}">Read more →</a>
        </p>
      </article>
    {% endfor %}
  </div>

</div>
