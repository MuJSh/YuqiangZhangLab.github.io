---
title: "People | 成员"
layout: gridlay
excerpt: "People"
sitemap: false
permalink: /people/
---

<style>
/* 整体容器更宽一点（可按需调节 1200–1320px） */
.people-container{ 
  max-width: 1280px; 
  margin: 0 auto; 
}

/* 加大列间距（覆盖 Bootstrap 默认 15px gutter） */
.people-row{ 
  margin-left: -30px; 
  margin-right: -30px; 
}
.people-row > [class*="col-"]{ 
  padding-left: 30px; 
  padding-right: 30px; 
}

/* 每个成员用横向布局，头像固定宽度，文本区域更宽 */
.people-card{ 
  display:flex; 
  align-items:flex-start; 
  gap:18px; 
  padding-bottom:28px; 
}
.people-card img{ 
  width:120px; 
  height:auto; 
  border-radius:16px; 
  margin:0; 
  float:none; 
}

/* 让文本更舒服 */
.people-card h4{ margin-top:0; }
.people-card p, .people-card br{ line-height:1.6; }

/* 小屏保持一列即可 */
@media (max-width: 767px){
  .people-card{ gap:14px; padding-bottom:22px; }
}
</style>


### Current group members

<div class="people-container">
{% assign number_printed = 0 %}
{% for member in site.data.people %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 0 %}
<div class="row people-row">
{% endif %}

<div class="col-sm-6">
  <div class="people-card">
    <img src="{{ site.url }}{{ site.baseurl }}/images/peopic/{{ member.photo }}" class="img-responsive" alt="{{ member.name }}" />
    <div>
      <h4>{{ member.name }}</h4>
      {{ member.info }}<br>

      {% if member.group_member == 1 %}
      <i>Email: {{ member.email }}</i><br>
      {% endif %}

      {% if member.number_educ %}
      <p>
      {{ member.education1 }} <br>
      {% if member.number_educ > 1 %}{{ member.education2 }} <br>{% endif %}
      {% if member.number_educ > 2 %}{{ member.education3 }} <br>{% endif %}
      {% if member.number_educ > 3 %}{{ member.education4 }} <br>{% endif %}
      {% if member.number_educ > 4 %}{{ member.education5 }} <br>{% endif %}
      {% if member.number_educ > 5 %}{{ member.education6 }} <br>{% endif %}
      {% if member.number_educ > 6 %}{{ member.education7 }} <br>{% endif %}
      </p>
      {% endif %}

      {% if member.group_member == 1 %}
      <p>{{ member.statement }}</p>
      {% endif %}
    </div>
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
</div>


<p></p>

### Alumni List

<div class="row">
<div class="col-sm-10 clearfix">

{% for alumni in site.data.alumni %}
  {{ alumni.name }}, {{ alumni.info }}, Now: {{ alumni.now }}.<br>
{% endfor %}

</div>
</div>
