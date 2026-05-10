---
title: "Publications"
excerpt: "Selected peer-reviewed work. Latest list on [Google Scholar](https://scholar.google.com/citations?user=rubyApkAAAAJ&hl=en)."
permalink: /publications/
layout: minimal
---

{%- assign all_pubs = site.data.publications -%}
{%- assign featured = all_pubs | where: "featured", true -%}

{%- comment -%} compute stats {%- endcomment -%}
{%- assign total_count = all_pubs | size -%}
{%- assign featured_count = featured | size -%}
{%- assign years = "" | split: "" -%}
{%- for p in all_pubs -%}
  {%- unless years contains p.year -%}
    {%- assign years = years | push: p.year -%}
  {%- endunless -%}
{%- endfor -%}
{%- assign years_sorted = years | sort -%}
{%- assign first_year = years_sorted | first -%}
{%- assign last_year = years_sorted | last -%}
{%- assign venues = "" | split: "" -%}
{%- for p in all_pubs -%}
  {%- unless venues contains p.venue -%}
    {%- assign venues = venues | push: p.venue -%}
  {%- endunless -%}
{%- endfor -%}
{%- assign awarded = all_pubs | where_exp: "p", "p.award" -%}
{%- assign award_count = awarded | size -%}

{%- comment -%} format short year range like "21–26" {%- endcomment -%}
{%- assign first_str = first_year | append: '' -%}
{%- assign last_str  = last_year  | append: '' -%}
{%- assign first_2 = first_str | slice: 2, 2 -%}
{%- assign last_2  = last_str  | slice: 2, 2 -%}

<div class="stats" data-reveal>
  <div class="stat"><span class="n">{{ total_count }}</span><span class="l">Papers</span></div>
  <div class="stat"><span class="n">'{{ first_2 }}–'{{ last_2 }}</span><span class="l">Active</span></div>
  <div class="stat"><span class="n">{{ venues | size }}</span><span class="l">Venues</span></div>
  <div class="stat"><span class="n">{{ award_count }}</span><span class="l">Award{% if award_count != 1 %}s{% endif %}</span></div>
</div>

{% include viz/pubs-chart.html %}

<p data-reveal style="font-family: var(--sans); font-size: 0.85rem; color: var(--muted); margin: 0 0 1.5rem;">
  Showing {{ featured_count }} of {{ total_count }} selected highlights. Full list on
  <a href="https://scholar.google.com/citations?user=rubyApkAAAAJ&hl=en">Google Scholar</a>.
</p>

<section class="pubs">
{%- assign last_year_shown = "" -%}
{%- assign sorted_featured = featured | sort: "year" | reverse -%}
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
