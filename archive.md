---
title: ""
show_hidden: false
---

<div> <h2> <a href="https://ofirsharony.github.io/about/"> Why Do I have a website?</a> </h2> </div>

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


<div>
  <h2>My Notable External Writing</h2>
  <ul>
    <li><a href="https://leaddev.com/career-development/leaders-journal-become-inspiring-leader-ten-minutes-day" target="_blank">
[Published at LeadDev.com] The leader’s journal: Become an inspiring leader in ten minutes a day</a></li>
    <li><a href="https://www.infoq.com/articles/in-app-subscriptions-made-easy/" target="_blank">
[Published at InfoQ] In-App Subscriptions Made Easy</a></li>
    <li><a href="https://medium.com/myheritage-engineering/kafka-to-bigquery-load-a-guide-for-streaming-billions-of-daily-events-cbbf31f4b737" target="_blank">
From Kafka to BigQuery: A Guide for Streaming Billions of Daily Events</a></li>
    <li><a href="https://medium.com/myheritage-engineering/achieving-real-time-analytics-via-change-data-capture-d69ed2ead889" target="_blank">
Achieving Real-time Analytics via Change Data Capture</a></li>
  </ul>
</div>