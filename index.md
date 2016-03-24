---
layout: default
title: Home
---

<div class="intro section">
  <img class="avatar" src="images/avatar240.jpg" alt="Jessica Parsons" />
  <p><span class="lead">I'm <strong>Jessica Parsons</strong>, and I've been professionally coding for the web since 2006.</span> My extensive knowledge
  of HTML, CSS, and SVG makes it easy for me to adapt to new frameworks and
  CMS platforms, ensuring wherever possible that the markup they generate is semantic, efficient, and accessible.</p>
  <p class="more-link">
    <a href="#about-me">More about me...</a>
  </p>

</div>

<hr class="section-divider">

<div class="projects section">
  <h2 class="section-title">Recent Projects</h2>
  <p>Click on a screenshot for more information.</p>
  <div class="posts">
    {% for post in site.tags.pro_projects limit:3 %}
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
    <a href="{{site.baseurl}}/projects/">More projects...</a>
  </p>
</div>

<hr class="section-divider">

<div class="projects section">
  <h2 class="section-title">Exercises and Experiments</h2>
  <p>Click on a screenshot for more information.</p>
  <div class="posts">
    {% for post in site.tags.experiments limit:3 %}
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
    <a href="{{site.baseurl}}/projects/">More projects...</a>
  </p>
</div>

<hr class="section-divider">

<div class="jobs section">
  <h2 class="section-title">Experience</h2>
  <div class="job-list">
    {% include job-list.html %}
  </div>
</div>


<hr class="section-divider">

<div class="education section">
  <h2 class="section-title">Education</h2>
  <div class="ed-list">
      {% include ed-list.html %}
  </div>
</div>

<hr class="section-divider">

<div class="about section" id="about-me">
  <h2 class="section-title">About Me</h2>
  <p>A lifelong learner, trained as a teacher, I'm a pattern seeker and a tinkerer with a passion for making things beautiful, functional, or delicious (and sometimes all three).</p>

  <p>Outside of work, I've baked and decorated wedding cakes, designed and sewn prize-winning garments, and taken apart and repaired all sorts of home appliances.  I've even had someone dress up as me for Halloween!</p>

  <p>I live in the beautiful San Francisco Bay Area and enjoy exploring its natural wonders with my shiba inus, <a href="http://miss-petunia.com">Petunia</a> and <a href="http://mr-monty.com">Monty</a>.</p>
</div>
