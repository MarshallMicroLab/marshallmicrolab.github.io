---
title: People
description: Meet the researchers, students, collaborators, and alumni who make up the Marshall Micro Lab.
permalink: /people/
---
{% assign categories = 'pi|Principal Investigator,faculty|Faculty,postdoc|Postdoctoral Researchers,graduate|Graduate Students,undergraduate|Undergraduate Researchers,staff|Staff,collaborator|Collaborators,alumni|Alumni' | split: ',' %}
{% for category_data in categories %}
  {% assign category = category_data | split: '|' %}
  {% assign people_in_category = site.people | where: 'category', category[0] | sort: 'order' %}
  {% if people_in_category.size > 0 %}
  <section class="people-group"><h2>{{ category[1] }}</h2><div class="card-grid card-grid-3">{% for person in people_in_category %}{% include person-card.html person=person %}{% endfor %}</div></section>
  {% endif %}
{% endfor %}