---
title: "Publications | 论文"
layout: gridlay
excerpt: "Publications"
sitemap: false
permalink: /publications/
---

<p></p>

(<b>XYZ-CHANGE members in bold</b>;)

<p></p>

{% for publication in site.data.publications %}

{{ publication.authors }}: <b>{{ publication.title }}</b>, <u><em>{{  publication.journal }}</em></u>, {{ publication.year }}. <a href="{{ publication.url }}">{{ publication.display }}</a>
<br /> 

{% endfor %}
