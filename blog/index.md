---
layout: default
title: Blog
---

<div class="section">

  <h1 class="page-title">{{ page.title }}</h1>

  <div class="posts">
    {% for post in site.categories.blog %}
    <div class="post">
      <h2 class="post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">
          {{ post.title }}
        </a>
      </h2>
      <span class="post-date">{{ page.date | date_to_string }}</span>
      <p class="post-description">{{ post.description }}</p>
    </div>
    {% endfor %}
  </div>

  <p class="more-link">
    <a href="{{site.baseurl}}/">Back to main page</a>
  </p>


</div>
