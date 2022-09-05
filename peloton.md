---
layout: page
title: Secret Peloton Page
permalink: /peloton/
sitemap: false
hide_contact_cta: true
image: /assets/img/peloton-cody.gif
---

Neil has taken a total of **{{ site.data.peloton.workoutTotals.Overall }}** Peloton classes, including {{ site.data.peloton.workoutTotals.Cycling }} cycle rides and {{ site.data.peloton.workoutTotals.Meditation }} meditations.

<div style="border-radius: 25px; border: 2px solid #396; padding: 10px;">
<img src="{{ site.data.peloton.latestRide.Photo }}"  style="float: left; border-radius: 50%; padding-right: 10pt;"/>
<h2>Latest Ride</h2>
<p><strong>Date/Time:</strong> {{ site.data.peloton.latestRide.Timestamp | date: "%-d %B %Y %H:%M" }}<br/>
<strong>Instructor:</strong> {{ site.data.peloton.latestRide.Instructor }}<br/>
<strong>Ride Name:</strong> {{ site.data.peloton.latestRide['Ride Name'] }}<br/>
<strong>Total Output:</strong> {{ site.data.peloton.latestRide['Total Output'] }}</p>
</div>
<br/>
## Top 10 Cycling Instructors
{% for instructor in site.data.peloton.totalsByInstructorAndDiscipline.Cycling limit: 10 %}
<strong>{{ instructor[0] }}</strong> ({{ instructor[1]}} classes)<br/>
{% endfor %}

## Personal Bests by Class Length

{% for distance in site.data.peloton.PBs %}

<div style="border-radius: 25px; border: 2px solid #396; padding: 10px;">
<img src="{{ distance[1].Photo }}"  style="float: left; border-radius: 50%; padding-right: 10pt"/>
<h2>{{ distance[0] }} PB:</h2>
<p><strong>Date/Time:</strong> {{ distance[1].Timestamp | date: "%-d %B %Y %H:%M" }}<br/>
<strong>Instructor:</strong> {{ distance[1].Instructor }}<br/>
<strong>Ride Name:</strong> {{ distance[1]['Ride Name'] }}<br/>
<strong>Total Output:</strong> {{ distance[1]['Total Output'] }}</p>
</div><br/>
{% endfor %}