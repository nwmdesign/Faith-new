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

### [{{ posts.title }}]({{ post.url | relative_url }})
{{ post.date | date: "%B %-d, %Y" }}
<img src="https://img.youtube.com/vi/{{ post.youtube }}/maxresdefault.jpg">

{% if sermon.series %}
Series: {{ post.series }}
{% endif %}

---

{% endfor %}

# Explore Sermons
[Browse by Topic]({{ "/topics/" | relative_url }})

[Browse by Date]({{ "/dates/" | relative_url }})
