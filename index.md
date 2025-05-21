---
layout: default
title: Home
---

# 👋 Welcome to Yaseer Arafat's Portfolio

## 🌟 Featured Posts

<ul>
  {% assign featured = site.posts | where: "featured", true %}
  {% if featured.size > 0 %}
    {% for post in featured %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <br><small>{{ post.date | date: "%B %d, %Y" }}</small>
      </li>
    {% endfor %}
  {% else %}
    <li>No featured posts yet.</li>
  {% endif %}
</ul>

## 📚 Recent Posts

<ul>
  {% for post in site.posts limit: 5 %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
