---
layout: page
title: Marshall Micro Lab
description: Microbial genomics, bioinformatics, and epidemiology at the University of Florida.
hero: true
---
<section class="home-hero">
  <div class="container hero-grid">
    <div>
      <p class="eyebrow">Marshall Micro Lab · University of Florida</p>
      <h1>Microbial genomics,<br><span>bioinformatics,</span> and epidemiology</h1>
      <p class="hero-copy">The Marshall Micro Lab develops and applies computational and genomic approaches to understand microbial populations, genomic diversity, transmission, and microbial epidemiology.</p>
      <div class="hero-actions"><a class="button" href="{{ '/research/' | relative_url }}">Explore our research</a><a class="text-link light-link" href="{{ '/people/' | relative_url }}">Meet the lab <span aria-hidden="true">→</span></a></div>
    </div>
    <aside class="affiliation-card">
      {% if site.logo %}<img src="{{ site.logo | relative_url }}" alt="Marshall Micro Lab logo">{% else %}<div class="hero-logo-placeholder" aria-label="Marshall Micro Lab logo placeholder"><span>MML</span><small>Logo</small></div>{% endif %}
      <p><a href="{{ site.mgm_url }}">Department of Molecular Genetics &amp; Microbiology <span aria-hidden="true">↗</span></a></p><p><a href="{{ site.epi_url }}">Emerging Pathogens Institute <span aria-hidden="true">↗</span></a></p><p><strong><a href="{{ site.uf_url }}">University of Florida <span aria-hidden="true">↗</span></a></strong></p>
    </aside>
  </div>
</section>

<section class="section intro-section"><div class="container narrow"><p class="eyebrow">Our work</p><h2>Connecting genomes, microbes, and place</h2><p class="section-lead">We combine microbial genomics, epidemiology, metagenomics, and reproducible software to study how microbial populations vary and move through hosts and environments.</p></div></section>

<section class="section section-tint"><div class="container"><div class="section-heading"><div><p class="eyebrow">Selected areas</p><h2>Research highlights</h2></div><a class="text-link" href="{{ '/research/' | relative_url }}">View all research <span aria-hidden="true">→</span></a></div><div class="card-grid card-grid-3">{% assign featured_research = site.research | where: 'featured', true | sort: 'order' %}{% for project in featured_research limit: 3 %}{% include research-card.html project=project %}{% endfor %}</div></div></section>

<section class="section"><div class="container"><div class="section-heading"><div><p class="eyebrow">Open and reproducible</p><h2>Software highlights</h2></div><a class="text-link" href="{{ '/software/' | relative_url }}">View all software <span aria-hidden="true">→</span></a></div><div class="card-grid card-grid-3">{% assign featured_software = site.software | where: 'featured', true | sort: 'order' %}{% for software in featured_software limit: 3 %}{% include software-card.html software=software %}{% endfor %}</div></div></section>

<section class="section section-navy"><div class="container"><div class="section-heading"><div><p class="eyebrow">Recent scholarship</p><h2>Latest publications</h2></div><a class="text-link light-link" href="{{ '/publications/' | relative_url }}">View all publications <span aria-hidden="true">→</span></a></div><div class="publication-list publication-list-dark">{% assign recent_publications = site.publications | sort: 'year' | reverse %}{% for publication in recent_publications limit: 3 %}{% include publication.html publication=publication %}{% endfor %}</div></div></section>

<section class="section"><div class="container"><div class="section-heading"><div><p class="eyebrow">From the lab</p><h2>Latest news</h2></div><a class="text-link" href="{{ '/news/' | relative_url }}">View all news <span aria-hidden="true">→</span></a></div><div class="card-grid card-grid-3">{% assign recent_news = site.news | sort: 'date' | reverse %}{% for post in recent_news limit: 3 %}{% include news-card.html post=post %}{% endfor %}</div></div></section>