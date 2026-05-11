---
title: "Publications"
excerpt: "Selected peer-reviewed work. Full list on [Google Scholar](https://scholar.google.com/citations?user=rubyApkAAAAJ&hl=en)."
permalink: /publications/
layout: minimal
---

{%- assign all_pubs = site.data.publications -%}
{%- assign featured = all_pubs | where: "featured", true -%}
{%- assign sorted_featured = featured | sort: "year" | reverse -%}

<p data-reveal style="font-family: var(--sans); font-size: 0.9rem; color: var(--muted); margin: 0 0 2rem;">
  A curated selection of {{ sorted_featured | size }} papers. The complete list lives on
  <a href="https://scholar.google.com/citations?user=rubyApkAAAAJ&hl=en">Google Scholar</a>.
</p>

<section class="pubs">
{%- assign last_year_shown = "" -%}
{%- for p in sorted_featured -%}
  {%- if p.year != last_year_shown %}

<h3 class="year" data-reveal>{{ p.year }}</h3>

  {%- assign last_year_shown = p.year -%}
  {%- endif %}

<div class="pub{% if p.award %} pub--award{% endif %}" data-reveal>
  <div class="title">{% if p.url %}<a href="{{ p.url }}">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</div>
  <div class="authors">{{ p.authors }}</div>
  <div class="venue">{{ p.venue }}{% if p.award %} <span class="award-badge">★ {{ p.award }}</span>{% endif %}</div>
</div>

{%- endfor %}
</section>
