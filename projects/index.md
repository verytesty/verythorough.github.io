---
layout: default
title: Projects
---

<div class="projects section">

  <h1 class="page-title">{{ page.title }}</h1>

  <p>Click on a screenshot for more information.</p>

  <div class="posts">
    {% for post in site.categories.projects %}
    <div class="post">
      <h3 class="post-title">
        <a href="{{ site.baseurl }}{{ post.url }}">
          <img class="project-thumb" src="{{ site.baseurl }}/images/{{ post.img_name }}-thumb.{{ post.img_type }}"
            alt="{{ post.title }} screenshot">
          {{ post.title }}
        </a>
      </h3>
      <p class="post-description">{{ post.description }}</p>
    </div>
    {% endfor %}
  </div>
  
  <p class="more-link">
    <a href="{{site.baseurl}}/">Back to main page</a>
  </p>


</div>