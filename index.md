---
layout: home
title: Watch Latest Sermon
---
{% assign latest = site.posts | sort: "date" | reverse | first %}

{% if latest %}

## {{ latest.title }}

{{ latest.date | date: "%B %-d, %Y" }}

{% if latest.series %}
**Series:** {{ latest.series }}
{% endif %}

{% if latest.youtube %}
<div class="youtube-wrapper">
  <iframe
    src="https://www.youtube.com/embed/{{ latest.youtube }}?rel=0"
    title="{{ latest.title }}"
    frameborder="0"
    allowfullscreen>
  </iframe>
</div>

{% endif %}

{% endif %}

[View Sermon Details]({{ latest.url | relative_url }})

---
---

<h2>More Sermons</h2>

{% assign recent = site.posts | sort: "date" | reverse %}

<div class="sermon-table">
  {% for post in recent limit:4 offset:1 %}
    <div class="sermon-cell">
      <h3>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>

      <p>{{ post.date | date: "%B %-d, %Y" }}</p>

      {% if post.scripture %}
        <p>{{ post.scripture }}</p>
      {% endif %}
    </div>
  {% endfor %}
</div>

# Explore Sermons
[Browse by Topic]({{ "/topics/" | relative_url }})


