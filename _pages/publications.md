---
title: "Publications"
layout: gridlay
excerpt: "Publications"
sitemap: false
permalink: /publications/
---

## Publications

Selected and recent publications are listed below. Group members are highlighted in bold where available in the publication database.

{% assign current_year = "" %}
{% for publication in site.data.publications %}
{% assign pub_year = publication.year | append: "" %}
{% if pub_year != current_year %}
{% assign current_year = pub_year %}

### {{ current_year }}
{% endif %}

{{ publication.authors }}. **{{ publication.title }}**. *{{ publication.journal }}*, {{ publication.year }}. {% if publication.url and publication.url != "" %}[{{ publication.display }}]({{ publication.url }}){% endif %}

{% endfor %}
