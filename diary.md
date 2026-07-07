---
layout: default
title: Diary
permalink: /diary/
---

<h1 class="page-title">Diary</h1>
<p class="page-note">Informal lab notes: experiments, reading, small findings. No comment section here — this notebook only speaks.</p>

<ul class="diary-list">
  {% assign entries = site.diary | sort: "date" | reverse %}
  {% for e in entries %}
  <li class="framed diary-row">
    <time class="mono" datetime="{{ e.date | date_to_xmlschema }}">{{ e.date | date: "%Y-%m-%d" }}</time>
    <a href="{{ e.url | relative_url }}">{{ e.title }}</a>
  </li>
  {% endfor %}
</ul>
