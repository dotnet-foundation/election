---
permalink: /campaign-2019/index.html
title: Campaign Statements
---

### Here are the campaign statements for our candidates.

Interested in running? Here's how to submit a campaign statement.

{% for candidate in site.campaign-2019 %}
* [{{ candidate.title }}]({{ candidate.url }})
{% endfor %}