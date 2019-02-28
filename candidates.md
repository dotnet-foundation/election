---
permalink: /candidates
title: Campaign Statements
---

{% if site.campaign-2019.size == 0 %}
### We're just getting started!

Hey, we just launched the election and are waiting for our first election statements. Interested in [joining the race?](/campaign)
{% else %}
### Here are the campaign statements for our candidates.
Interested in joining the race? [Here's how to get started](/campaign).
  {% for candidate in site.campaign-2019 %}
  * [{{ candidate.title }}]({{ candidate.url }})
  {% endfor %}
{% endif %}