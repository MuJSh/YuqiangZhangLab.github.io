---
title: "Conferences"
layout: textlay
excerpt: "Conferences"
sitemap: false
permalink: /conferences/
---

## Conferences and Meetings

This page records conferences, workshops, group meetings, and other academic activities involving the lab.

### Conferences

{% for item in site.data.conferences %}

**{{ item.date }}**  
**{{ item.title }}**  
{% if item.role and item.role != "" %}{{ item.role }}{% endif %}{% if item.location and item.location != "" %}, {{ item.location }}{% endif %}{% if item.link and item.link != "" %}  
[More information]({{ item.link }}){% endif %}

{% endfor %}

### Group Meeting Schedule

Regular group meetings are held weekly. The schedule may be updated according to teaching, fieldwork, conference travel, and project deadlines.

{% for meeting in site.data.group_meetings %}
{% if meeting.date and meeting.date != "" %}

**{{ meeting.date }}**  
{{ meeting.presenter }}

{% endif %}
{% endfor %}
