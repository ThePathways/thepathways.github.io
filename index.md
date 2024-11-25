---
layout: default
---






   <center>It’s 2006, and I wrote my first program on the job. Since then, I’ve explored various roles in the tech industry—from software engineer to architect, software manager, and program manager—working in both startups and Fortune 100 companies. Throughout this journey, I’ve gathered invaluable lessons that I believe can benefit both seasoned professionals and newcomers alike.
<br/>
This is the place where I am writing and compiling all my old notes, insights, and experiences. My goal is to create a resource that not only reflects my growth but also serves as a guide for others navigating their own paths in the tech world. Whether you’re just starting or looking to deepen your expertise, I hope you find valuable takeaways that resonate with your journey.
<br/>
Thank you for joining me! I encourage you to share your thoughts, experiences, and questions. Let’s connect, inspire one another, and stay tuned for more posts!
</center>


{% assign categories = site.posts | group_by: "category" %}
{% for category in categories %}
## {{ category.name }} <!-- ({{ category.items.size }} articles) --> 
{% assign sorted_articles = category.items | sort: 'date' | reverse %}
{% if sorted_articles.size > 0 %}
<div>
<ul style="list-style-type: none; padding: 0; margin: 0;">
{% for article in sorted_articles %}
    <li>
        <a href="{{ article.url }}" target="_blank" rel="noopener noreferrer">{{ article.title }}</a>  <small> - {{ article.date | date: "%B %d, %Y" }}</small>
    </li>
{% endfor %}
</ul>
</div>
{% else %}
<p>No articles available in this category.</p>
{% endif %}
{% endfor %}


