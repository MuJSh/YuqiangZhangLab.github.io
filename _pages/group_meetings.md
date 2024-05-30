---
title: "Group meettings | 组会"
layout: textlay
excerpt: "Group Meetings"
sitemap: false
permalink: /group_meetings/
---

## Group Meeting Schedule

Group meettings are held every week.   

The normal time/place is 9:00 am in K6-330.  

<b>Schedule is subject to change, please check frequently. </b>

{% for meeting in site.data.group_meetings %}

<b>{{ meeting.date}}</b>  {{ meeting.presenter}}
<br /> 

{% endfor %}
