---
layout: default
title: Home
---

<section style="text-align: center; padding: 2rem 1rem;">
  <h1 style="font-size: 2.5rem; margin-bottom: 0.5rem;">👋 Hello, I'm <strong>Yaseer Arafat</strong></h1>
  <p style="font-size: 1.2rem; color: #555;">A .NET Software Architect, Open Source Contributor & Tech Educator</p>
</section>

<hr style="margin: 2rem auto; width: 60%;">

<section style="padding: 1rem 2rem;">
  <h2>🚀 Featured Posts</h2>
  <ul style="list-style-type: none; padding-left: 0;">
    {% for post in site.posts %}
    <li style="margin-bottom: 1rem;">
      <a href="{{ post.url }}" style="font-size: 1.2rem; font-weight: bold; text-decoration: none;">
        {{ post.title }}
      </a>
      {% if post.excerpt %}
        <p style="margin: 0.25rem 0 0; color: #666;">{{ post.excerpt | strip_html | truncate: 150 }}</p>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</section>

<hr style="margin: 2rem auto; width: 60%;">

<section style="padding: 1rem 2rem;">
  <h2>👨‍💻 About This Site</h2>
  <p>This is my personal tech portfolio and blog — where I share thoughts, code, and experiments on modern .NET, software architecture, and AI-driven systems. If you care about clean code, performance, and pragmatic innovation, you're in the right place.</p>
</section>

<hr style="margin: 2rem auto; width: 60%;">

<section style="padding: 1rem 2rem;">
  <h2>📬 Connect with Me</h2>
  <ul style="list-style: none; padding-left: 0;">
    <li><a href="https://github.com/emonarafat" target="_blank">GitHub</a></li>
    <li><a href="https://linkedin.com/in/yaseerarafat" target="_blank">LinkedIn</a></li>
    <li><a href="https://twitter.com/emontwitts" target="_blank">Twitter</a></li>
    <li>Email: <a href="mailto:yaseer.arafat@live.com">yaseer.arafat@live.com</a></li>
  </ul>
</section>

<footer style="text-align: center; margin-top: 2rem; font-size: 0.9rem; color: #999;">
  <p>© {{ site.time | date: '%Y' }} Yaseer Arafat. All rights reserved.</p>
</footer>
