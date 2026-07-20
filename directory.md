---
layout: default
title: Directory
permalink: /directory/
---

<div class="eyebrow">Who's involved</div>
<h1>Directory</h1>
<p>Everyone working on environmental DNA at CRBE Toulouse, and what they're focused on.</p>
<p><a href="https://docs.google.com/forms/d/e/1FAIpQLSfqFDzKeap8hiRMraCo3jbCdAKmVvMrIlTubhgIG-Av5toq5Q/viewform?usp=dialog">Not listed yet? Fill out this form to join →</a></p>

<div class="domain-key">
  <span><i class="dot air"></i>Air</span>
  <span><i class="dot soil"></i>Soil</span>
  <span><i class="dot freshwater"></i>Freshwater</span>
  <span><i class="dot marine"></i>Marine</span>
  <span><i class="dot microbiome"></i>Microbiome</span>
</div>

<div class="member-grid">
{% for member in site.membres %}
  {% assign n = member.edna_domains.size %}
  {% assign slice = 360 | divided_by: n %}
  {% assign gradient = "" %}
  {% for domain in member.edna_domains %}
    {% assign start = forloop.index0 | times: slice %}
    {% assign end = forloop.index | times: slice %}
    {% if forloop.last %}{% assign end = 360 %}{% endif %}
    {% assign piece = "var(--" | append: domain | append: ") " | append: start | append: "deg " | append: end | append: "deg" %}
    {% if gradient == "" %}
      {% assign gradient = piece %}
    {% else %}
      {% assign gradient = gradient | append: ", " | append: piece %}
    {% endif %}
  {% endfor %}
  <div class="member-card">
    <div class="avatar-ringed" style="background: conic-gradient({{ gradient }});">
      <div class="avatar">
        {% if member.consent_photo %}
          <img src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
        {% endif %}
      </div>
    </div>
    <h3>{{ member.name }}</h3>
    <p class="topic">{{ member.research_topic }}</p>
    <div class="tags">
      {% for domain in member.edna_domains %}
        <span class="tagdot" style="background: var(--{{ domain }})"></span>
      {% endfor %}
    </div>
  </div>
{% endfor %}
</div>
