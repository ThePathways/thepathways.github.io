---
layout: default
title: Home
---




## About

It’s 2006, I wrote my first program on the job. Since then, I’ve explored various roles in the tech industry—from software engineer to architect, software manager, and program manager—working in both startups and Fortune 100 companies. Throughout this journey, I’ve gathered invaluable lessons that I believe can benefit both seasoned professionals and newcomers alike.

I’m excited to embark on this blogging adventure and share my insights with you. My goal is to connect with fellow developers, learn from your experiences, and contribute to our vibrant community of software engineers. Whether you’re just starting out or are a seasoned professional, I invite you to join me on this journey. Together, we can navigate the ever-evolving world of technology, fostering a supportive space where we can all learn and grow.

Thank you for joining me! I encourage you to share your thoughts, experiences, and questions in the comments. Let’s connect, inspire one another, and stay tuned for more posts!


{% assign categories = site.posts | group_by: "category" %}
{% for category in categories %}
## {{ category.name }} <!-- ({{ category.items.size }} articles) --> 
{% assign sorted_articles = category.items | sort: 'date' | reverse %}
{% if sorted_articles.size > 0 %}
<div>
<ul style="list-style-type: none; padding: 0; margin: 0;">
{% for article in sorted_articles %}
    <li>
        <a href="{{ article.url }}" target="_blank" rel="noopener noreferrer">{{ article.title }}</a>  <sub> - {{ article.date | date: "%B %d, %Y" }}</sub>
    </li>
{% endfor %}
</ul>
</div>
{% else %}
<p>No articles available in this category.</p>
{% endif %}
{% endfor %}


