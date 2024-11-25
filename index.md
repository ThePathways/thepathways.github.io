---
layout: default
title: Home
---




{% assign categories = site.posts | group_by: "category" %}
{% for category in categories %}
## {{ category.name }} <!-- ({{ category.items.size }} articles) --> 
{% assign sorted_articles = category.items | sort: 'date' | reverse %}
{% if sorted_articles.size > 0 %}
<div>
<ul style="list-style-type: none; padding: 0; margin: 0;">
{% for article in sorted_articles %}
    <li>
        <a href="{{ article.url }}" target="_blank" rel="noopener noreferrer">{{ article.title }}</a> - {{ article.date | date: "%B %d, %Y" }}
    </li>
{% endfor %}
</ul>
</div>
{% else %}
<p>No articles available in this category.</p>
{% endif %}
{% endfor %}


