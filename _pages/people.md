---
title: "Group Members"
layout: gridlay
excerpt: "Group Members"
sitemap: false
permalink: /group-members/
---

<style>
.member-block {
  margin-bottom: 28px;
}
.member-card {
  min-height: 210px;
  margin-bottom: 28px;
}
.member-card img {
  float: left;
  width: 150px;
  margin: 0 16px 10px 0;
  border-radius: 12px;
}
.member-name {
  font-size: 1.1em;
  font-weight: 600;
  margin-bottom: 4px;
}
.member-role {
  color: #555;
  margin-bottom: 4px;
}
.alumni-line {
  margin-bottom: 8px;
}
</style>

## Principal Investigator

{% for member in site.data.people %}
{% if member.name contains "Yuqiang Zhang" %}
<div class="member-block clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/peopic/{{ member.photo }}" class="img-responsive" width="180" style="float:left; margin:0 20px 12px 0; border-radius:12px;" />
  <div class="member-name">{{ member.name }}</div>
  <div class="member-role">{{ member.info }}</div>
  <i>Email: {{ member.email }}</i><br>
  {% if member.number_educ %}
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
  {% if member.statement and member.statement != "" %}<p>{{ member.statement }}</p>{% endif %}
</div>
{% endif %}
{% endfor %}

## Current Group Members

{% assign number_printed = 0 %}
{% for member in site.data.people %}
{% unless member.name contains "Yuqiang Zhang" %}
{% if member.group_member == 1 %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
<div class="row" style="margin-left:-30px;margin-right:-30px;">
{% endif %}

<div class="col-sm-6 clearfix member-card" style="padding-left:30px;padding-right:30px;">
  <img src="{{ site.url }}{{ site.baseurl }}/images/peopic/{{ member.photo }}" class="img-responsive" alt="{{ member.name }}" />
  <div class="member-name">{{ member.name }}</div>
  <div class="member-role">{{ member.info }}</div>
  {% if member.email and member.email != "" %}<i>Email: {{ member.email }}</i><br>{% endif %}
  {% if member.number_educ %}
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
  {% if member.statement and member.statement != "" %}<p>{{ member.statement }}</p>{% endif %}
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endunless %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

## Alumni

{% for alumni in site.data.alumni %}
<div class="alumni-line">
  {{ alumni.name }}, {{ alumni.info }}, Now: {{ alumni.now }}.
</div>
{% endfor %}
