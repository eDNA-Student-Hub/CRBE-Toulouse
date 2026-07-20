---
layout: default
title: Summaries
permalink: /summaries/
---

<div class="eyebrow">Session recaps</div>
<h1>Summaries</h1>
<p>What came out of each session — published within a few days.</p>

{% assign done = site.sujets | where: "status", "done" | sort: "date" | reverse %}
{% for sujet in done %}
  <div style="margin-bottom: 32px; padding-bottom: 32px; border-bottom: 1px solid var(--line);">
    <span class="topic-meta">{{ sujet.date }}</span>
    <h3 style="margin-top: 8px;">{{ sujet.title }}</h3>
    <p style="color: var(--ink-soft); margin-top: 10px;">{{ sujet.summary }}</p>
  </div>
{% endfor %}
