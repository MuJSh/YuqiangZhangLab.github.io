---
title: "Publications | 论文"
layout: gridlay
excerpt: "Publications"
sitemap: false
permalink: /publications/
---

<p></p>

(<b>ACMRSG members in bold</b>; <b>*</b> Lei Zhu as the corresponding author)

<p></p>

{% for publication in site.data.publications %}

{{ publication.authors }}: <b>{{ publication.title }}</b>, <u><em>{{  publication.journal }}</em></u>, {{ publication.year }}. <a href="{{ publication.url }}">{{ publication.display }}</a>
<br /> 

{% endfor %}
