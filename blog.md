---
layout: page
title: Blog
permalink: /blog/
---

<div class="blog-header">
  <h1>All Blog Posts</h1>
  <p>Thoughts, tutorials, and insights about web development and technology.</p>
</div>

{% if site.posts.size > 0 %}
  <ul class="post-list">
    {% for post in site.posts %}
    <li>
      <div class="post-meta">{{ post.date | date: "%b %-d, %Y" }} • {{ post.read_time | default: "5 min read" }}</div>
      <h2><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h2>
      <p>{{ post.excerpt | strip_html | truncatewords: 40 }}</p>
      {% if post.tags.size > 0 %}
        <div class="post-tags">
          {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
{% else %}
  <p>No posts yet. Check back soon!</p>
{% endif %}