---
title: "News"
layout: gridlay
excerpt: "News"
sitemap: false
permalink: /news/
---

## News

{% for article in site.data.news %}

**{{ article.date }}**  
{{ article.headline }}

{% endfor %}
