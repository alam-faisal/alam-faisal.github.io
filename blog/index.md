---
layout: single
title: "Blog"
permalink: /blog/
author_profile: true
---

<style>
  .blog-container {
    max-width: 800px;
    margin: 0 auto;
    padding: 10px 20px;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  }

  .blog-post {
    margin-bottom: 30px;
  }

  .blog-post-title {
    font-size: 1.05em;
    color: #1e40af;
    text-decoration: none;
  }

  .blog-post-title:hover {
    color: #2563eb;
    text-decoration: underline;
  }

  .blog-post-excerpt {
    font-size: 0.95em;
    color: #444;
    margin-top: 5px;
  }

  .page-title {
    text-align: center;
    margin-bottom: 30px;
  }
</style>

<div class="page-title">
  <h1>Blog</h1>
</div>

<div class="blog-container">
  {% for post in site.posts %}
    <div class="blog-post">
      <a class="blog-post-title" href="{{ post.url }}">{{ post.title }}</a>
      <p class="blog-post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </div>
  {% endfor %}
</div>
