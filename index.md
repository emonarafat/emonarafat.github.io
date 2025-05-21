---
layout: default
title: Home
---

# Welcome to Yaseer Arafat's Portfolio and Blog

## Featured Posts

<ul>
  {% assign featured_posts = site.posts | where: "featured", true %}
  {% if featured_posts.size > 0 %}
    {% for post in featured_posts %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <small>— {{ post.date | date: "%b %d, %Y" }}</small>
      </li>
    {% endfor %}
  {% else %}
    <li>No featured posts available yet.</li>
  {% endif %}
</ul>

## Latest Posts

<ul>
  {% for post in site.posts limit:5 %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
