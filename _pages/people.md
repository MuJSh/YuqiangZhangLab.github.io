---
title: "People | 成员"
layout: gridlay
excerpt: "People"
sitemap: false
permalink: /people/
---

### Current group members

{% assign number_printed = 0 %}
{% for member in site.data.people %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
<div class="row" style="margin-left:-30px;margin-right:-30px;">
{% endif %}

<div class="col-sm-6 clearfix" style="padding-left:30px;padding-right:30px;">
  <img src="{{ site.url }}{{ site.baseurl }}/images/peopic/{{ member.photo }}" 
       class="img-responsive" width="120" 
       style="float: left; margin: 0 16px 8px 0; border-radius:12px; vertical-align: top;" />

  <div style="overflow: hidden;">
    <h4>
      {% if member.url %}
        <a href="{{ member.url }}" target="_blank">{{ member.name }}</a>
      {% else %}
        {{ member.name }}
      {% endif %}
    </h4>

    {{ member.info }}<br>

    {% if member.group_member == 1 and member.email != "" %}
      <i>Email: {{ member.email }}</i><br>
    {% endif %}

    {% if member.number_educ > 0 %}
      <p>
        {{ member.education1 }}<br>
        {% if member.number_educ > 1 %}{{ member.education2 }}<br>{% endif %}
        {% if member.number_educ > 2 %}{{ member.education3 }}<br>{% endif %}
        {% if member.number_educ > 3 %}{{ member.education4 }}<br>{% endif %}
        {% if member.number_educ > 4 %}{{ member.education5 }}<br>{% endif %}
        {% if member.number_educ > 5 %}{{ member.education6 }}<br>{% endif %}
        {% if member.number_educ > 6 %}{{ member.education7 }}<br>{% endif %}
      </p>
    {% endif %}

    {% if member.group_member == 1 and member.statement != "" %}
      <p>{{ member.statement }}</p>
    {% endif %}
  </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p></p>

### Alumni List

<div class="row">
  <div class="col-sm-10 clearfix">
    {% for alumni in site.data.alumni %}
      {{ alumni.name }}, {{ alumni.info }}, Now: {{ alumni.now }}.<br>
    {% endfor %}
  </div>
</div>
