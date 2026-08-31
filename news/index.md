---
title: News
description: Updates, announcements, and milestones from the lab.
permalink: /news/
---
<div class="news-list">{% assign updates = site.news | sort: 'date' | reverse %}{% for post in updates %}{% include news-card.html post=post %}{% endfor %}</div>