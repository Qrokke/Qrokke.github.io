---
layout: default
title: Publications
permalink: /publications/
---

<h1 class="page-title">Publications</h1>
<p class="page-note">Author-name bolding follows the byline of each paper. Peer-reviewed unless noted otherwise.</p>

{% assign categories = "journal|Journal Articles,international|International Conferences,domestic|Domestic Conferences,poster|Posters & Demos,misc|Miscellaneous" | split: "," %}

{% for pair in categories %}
  {% assign key = pair | split: "|" | first %}
  {% assign label = pair | split: "|" | last %}
  {% assign items = site.data.publications | where: "category", key | sort: "year" | reverse %}
  {% if items.size > 0 %}
<section class="pub-section framed">
  <h2>{{ label }}</h2>
  <ol class="pub-list" reversed>
    {% for p in items %}
    <li class="pub">
      <p class="pub-authors">{{ p.authors }}</p>
      <p class="pub-title">&ldquo;{{ p.title }}&rdquo;</p>
      <p class="pub-venue">
        <em>{{ p.venue }}</em>, {{ p.year }}{% if p.in_japanese %} <span class="lang-note">(in Japanese)</span>{% endif %}{% if p.status %} <span class="status mono">[{{ p.status }}]</span>{% endif %}{% if p.note %} — {{ p.note }}{% endif %}
      </p>
      {% if p.doi or p.url or p.pdf %}
      <p class="pub-links mono">
        {% if p.doi %}<a class="chip" href="https://doi.org/{{ p.doi }}" rel="noopener">DOI</a>{% endif %}
        {% if p.url %}<a class="chip" href="{{ p.url }}" rel="noopener">Link</a>{% endif %}
        {% if p.pdf %}<a class="chip" href="{{ p.pdf }}" rel="noopener">PDF</a>{% endif %}
      </p>
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>
  {% endif %}
{% endfor %}
