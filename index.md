---
layout: default
title: Home
---


## About

I’m excited to embark on this journey and share it with you. I hope to connect with fellow developers, learn from their experiences, and contribute to the vibrant community of software engineers. If you’re just starting out or are a seasoned professional, I invite you to join me on this adventure.

Let’s stay tuned and connected as we navigate the ever-evolving world of technology together. I encourage you to share your thoughts, experiences, and questions in the comments. Together, we can foster a supportive community where we learn and grow.

Thank you for reading, and stay tuned for more posts!


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


