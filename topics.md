---
layout: default
title: "Topics"
---

<h2>Sermon Topics</h2>

<ul class="topic-list">
  {% assign topics = site.tags | sort %}
  
  {% for topic in topics %}
    <li>
      <a href="/tags/{{ topic[0] | slugify }}/">
        {{ topic[0] }}
      </a>
    </li>
  {% endfor %}
</ul>




