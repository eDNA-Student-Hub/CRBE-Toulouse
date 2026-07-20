---
layout: default
title: Directory
permalink: /directory/
---

<div class="eyebrow">Who's involved</div>
<h1>Directory</h1>
<p>Everyone working on environmental DNA at CRBE Toulouse, and what they're focused on.</p>
<p><a href="https://docs.google.com/forms/d/e/1FAIpQLSfqFDzKeap8hiRMraCo3jbCdAKmVvMrIlTubhgIG-Av5toq5Q/viewform?usp=dialog">Not listed yet? Fill out this form to join →</a></p>

<div class="member-grid">
{% for member in site.membres %}
  <div class="member-card">
    <div class="avatar">
      {% if member.consent_photo %}
        <img src="{{ member.photo | relative_url }}" alt="{{ member.name }}">
      {% endif %}
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
