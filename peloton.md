---
layout: page
title: Secret Peloton Page
permalink: /peloton/
sitemap: false
hide_contact_cta: true
image: /assets/img/peloton-cody.gif
---

Very much under construction!

{% for stat in site.data.peloton.workoutTotals %}
**{{ stat[0] }}**: {{ stat[1] }}
{% endfor %}

{% for distance in site.data.peloton.PBs %}
**{{ distance[0] }}min PB**: {{ distance[1]['Ride Name'] }} with {{ distance[1].Instructor }} ({{ distance[1]['Total Output']}}kJ)
{% endfor %}