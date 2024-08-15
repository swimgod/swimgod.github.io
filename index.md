---
layout: single
author_profile: true
title: Projects
---

{% for post in site.posts %}
  <article>
    <h4>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h4>
  </article>
{% endfor %}