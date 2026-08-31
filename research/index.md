---
title: Research
description: We use genomic and computational approaches to investigate microbial diversity, transmission, and ecology.
permalink: /research/
---
<div class="card-grid card-grid-2">
{% assign projects = site.research | sort: 'order' %}
{% for project in projects %}{% include research-card.html project=project %}{% endfor %}
</div>