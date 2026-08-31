---
title: Publications
description: Publications from the Marshall Micro Lab, listed newest first.
permalink: /publications/
---
{% assign publications = site.publications | sort: 'year' | reverse %}
{% assign publications_by_year = publications | group_by: 'year' %}
{% for year in publications_by_year %}<section class="publication-year"><h2>{{ year.name }}</h2><div class="publication-list">{% for publication in year.items %}{% include publication.html publication=publication %}{% endfor %}</div></section>{% endfor %}