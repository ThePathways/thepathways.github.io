---
layout: home
title: Home
---




{% assign categories = site.posts | group_by: "category" %}

{% for category in categories %}
## {{ category.name }}

{% assign sorted_articles = category.items | sort: 'date' | reverse %}  <!-- Sort articles by date in reverse order -->

<div>
<ul>
{% for article in sorted_articles %}
    <li>
        <a href="{{ article.url }}">{{ article.title }}</a>
    </li>
{% endfor %}
</ul>
</div>

{% endfor %}


