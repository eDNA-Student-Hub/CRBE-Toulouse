---
layout: default
title: Topics
permalink: /topics/
---

<div class="eyebrow">Discussion topics</div>
<h1>Topics</h1>
<p>What's coming up, and what we've already covered. Want to suggest one? <a href="https://github.com/eDNA-Student-Hub/CRBE-Toulouse/issues/new/choose">Open a topic here →</a></p>

<div class="topic-list">
{% assign sujets = site.sujets | sort: "date" | reverse %}
{% for sujet in sujets %}
  <div class="topic-row">
    <span class="topic-label {{ sujet.status }}">{{ sujet.status }}</span>
    <span class="topic-title">{{ sujet.title }}</span>
    <span class="topic-meta">{{ sujet.date }}</span>
  </div>
{% endfor %}
</div>
