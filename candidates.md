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

[![Gitter](https://badges.gitter.im/dotnet-foundation/election.svg)](https://gitter.im/dotnet-foundation/election?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

<section class="card-container">
  {% for candidate in site.campaign-2019 %}
    <article class="card">
        <header class="card__title">
            <h3>{{ candidate.title }}</h3>
        </header>
        <figure class="card__thumbnail">
          {% if candidate.image %}
            <img src="{{ candidate.image }}">
          {% else %}
            <img src="/img/dot_bot.png">
          {% endif %}
        </figure>
        <a href="{{ candidate.url }}" class="card__button">Learn More</a>
    </article>
  {% endfor %}
</section>

{% endif %}

<script type="text/javascript">
document.addEventListener('DOMContentLoaded', function() {
  var cookieName = 'candidates';
  var cookie = Cookies.getJSON(cookieName);
  var ul = document.querySelector('section.card-container');
  
  var values = new Array();
  for (var i = 0; i < ul.children.length; i++) {
    values.push(Math.random() * i | 0);
  }
  console.log(cookie);
  if (cookie != null && values.length == cookie.values.length) {
    /* reset if candidate lengths change */
    values = cookie.values;
  } else {
    Cookies.set(cookieName, { values : values }, { expires: 1 /*days*/ });
  }

  for(var i=0; i < values.length; i++) {
    ul.appendChild(ul.children[values[i] | 0]);
  }
}, false);
</script>
