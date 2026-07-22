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
<iframe
width="650"
height="366"
src="https://www.youtube.com/embed/{{ latest.youtube }}"
title="{{ latest.title }}"
frameborder="0"
allowfullscreen>
</iframe>
{% endif %}

{% endif %}

[View Sermon Detials]({{ latest.url | relative_url }})

---

## More Sermons

{% assign recent = site.posts | sort: "date" | reverse %}

{% for post in recent limit:4 offset:1 %}

### [{{ post.title }}]({{ post.url | relative_url }})
{{ post.date | date: "%B %-d, %Y" }}

{% if sermon.series %}
Series: {{ post.series }}
{% endif %}

---

{% endfor %}

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

[Browse by Date]({{ "/dates/" | relative_url }})
