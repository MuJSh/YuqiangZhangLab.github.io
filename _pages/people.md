---
title: "People | 成员"
layout: gridlay
excerpt: "People"
sitemap: false
permalink: /people/
---

### Current group members

<div class="row">
  {% for member in site.data.people %}
    <div class="col-sm-6" style="margin-bottom: 20px;">
      <div style="display: flex; align-items: flex-start; background-color: #fff; border-radius: 10px; padding: 16px; border: 1px solid #eee; box-shadow: 0 1px 3px rgba(0,0,0,0.05);">
        <img src="{{ site.url }}{{ site.baseurl }}/images/peopic/{{ member.photo }}" width="120" style="border-radius: 12px; margin-right: 16px;" />
        
        <div style="max-width: calc(100% - 136px); word-break: break-word;">
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
    </div>
  {% endfor %}
</div>

### Alumni List

<div class="row">
  <div class="col-sm-10 clearfix">
    {% for alumni in site.data.alumni %}
      {{ alumni.name }}, {{ alumni.info }}, Now: {{ alumni.now }}.<br>
    {% endfor %}
  </div>
</div>
