---
layout: page
title: Secret Peloton Page
permalink: /peloton/
sitemap: false
hide_contact_cta: true
image: /assets/img/peloton-cody.gif
---

Neil has taken a total of **{{ site.data.peloton.workoutTotals.Overall }}** Peloton classes, including {{ site.data.peloton.workoutTotals.Cycling }} cycle rides (covering {% include peloton-mileage-formatted.html %} miles) and {{ site.data.peloton.workoutTotals.Meditation }} meditations.

<div style="border-radius: 25px; border: 2px solid #396; padding: 10px;">
<img src="{{ site.data.peloton.latestRide.Photo }}"  style="float: left; border-radius: 50%; padding-right: 10pt;"/>
<h2>Latest Ride</h2>
{% assign avgPerMin = site.data.peloton.latestRide['Total Output'] | plus: 0.0 | divided_by: site.data.peloton.latestRide.Length | round: 1 %}
<p><strong>{{ site.data.peloton.latestRide['Ride Name'] }} with {{ site.data.peloton.latestRide.Instructor }}</strong>
{% if site.data.peloton.latestRide['Live Ride'] %}
<span class="highlight">LIVE</span>
{% endif %}
{% if site.data.peloton.latestRide.Timestamp == site.data.peloton.PBs[site.data.peloton.latestRide.Length].Timestamp %}
<span class="highlight">🥇 PB</span>
{% endif %}
<br/>
{{ site.data.peloton.latestRide.Timestamp | date: "%-d %B %Y at %H:%M" }}<br/>
Total Output: {{ site.data.peloton.latestRide['Total Output'] }}kJ ({{ avgPerMin }}kJ/min)</p>
</div>
<br/>
## Top 10 Cycling Instructors
{% for instructor in site.data.peloton.totalsByInstructorAndDiscipline.Cycling limit: 10 %}
<strong>{{ forloop.index }}: {{ instructor[0] }}</strong> ({{ instructor[1]}} classes)<br/>
{% endfor %}
<br/>

## Top 5 Meditation Instructors
{% for instructor in site.data.peloton.totalsByInstructorAndDiscipline.Meditation limit: 5 %}
<strong>{{ forloop.index }}: {{ instructor[0] }}</strong> ({{ instructor[1]}} classes)<br/>
{% endfor %}
<br/>
## Personal Bests by Class Length

{% for distance in site.data.peloton.PBs %}
{% assign avgPerMin = distance[1]['Total Output'] | plus: 0.0 | divided_by: distance[0] | round: 1 %}
<div style="border-radius: 25px; border: 2px solid #396; padding: 10px;">
<img src="{{ distance[1].Photo }}"  style="float: left; border-radius: 50%; padding-right: 10pt"/>
<h2>{{ distance[0] }}min PB:</h2>
<p><strong>{{ distance[1]['Ride Name'] }} with {{ distance[1].Instructor }}</strong>
{% if distance[1]['Live Ride'] %}
<span class="highlight">LIVE</span>
{% endif %}
<br/>
{{ distance[1].Timestamp | date: "%-d %B %Y at %H:%M" }}<br/>
Total Output: {{ distance[1]['Total Output'] }}kJ ({{ avgPerMin }}kJ/min)</p>
</div><br/>
{% endfor %}