---
layout: page
title: Neil 💓 Peloton
permalink: /peloton/
sitemap: false
hide_contact_cta: true
image: /assets/img/peloton-cody.gif
---

If you've found this page, congratulations! Either you've diligently read through every last paragraph on the [About page](/about), or you've been browsing our source code on GitHub; I wonder what other treats are hidden away on there?

One of the downsides of Peloton is that they don't have the concept of a "public profile" to show-off your stats; it's one of the ways that they get you to buy into their ecosystem. ("Want to see stats? Sign up then!")

So, I built a stack to game the system a bit:
* I created a webpage (not this one) which, when loaded, connects to my Peloton account, downloads a huge CSV of all my workouts, extracts key information (including, for instance, calculating all of my personal bests) and outputs the result in a chunk of JSON.
* I created a GitHub action (well, I utilised [this one](https://github.com/TheLastProject/keep-remote-file-locally-up-to-date-action)) to connect to my page, read the JSON, and detect if it's different to the last version that it saw. If there are differences, it saves the JSON into a static file in my GitHub repo.
* When serving this site (and specifically rendering this page), Jekyll reads the data out of the static file. (GitHub Pages forbids the use of random gems, otherwise I could've just used [this one](https://github.com/brockfanning/jekyll-get-json) and bypassed the need for a static file.)

With all that in mind, below are all of the latest statistics - currently updated nightly.

## Neil's Peloton statistics

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