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
  <div class="member-card">
    <div class="avatar" style="border: 2.5px solid var(--{{ member.edna_domains.first }});">
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
</div>var(--{{ domain }})"></span>
      {% endfor %}
    </div>
  </div>
{% endfor %}
</div>
