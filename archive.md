---
title: "Archive"
show_hidden: false
---

{% assign show_hidden = page.show_hidden %}

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
<h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      {% if show_hidden or post.hidden != true %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
