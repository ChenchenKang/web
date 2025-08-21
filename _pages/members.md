---
layout: single
title: "Members"
permalink: /members/
author_profile: true
---

<!-- Simple, responsive card grid -->
<style>
.members-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 1.25rem; }
.member-card { background: var(--mm-surface, #fff); border-radius: 12px; padding: 16px; box-shadow: 0 1px 6px rgba(0,0,0,.06); text-align: center; }
.member-photo { width: 120px; height: 120px; border-radius: 50%; object-fit: cover; display: block; margin: 0 auto 10px; }
.member-name { font-weight: 700; margin: 4px 0; }
.member-meta { color: #666; font-size: .95rem; margin: 2px 0; }
.member-tags { font-size: .9rem; margin-top: 6px; }
.member-links a { text-decoration: none; }
.member-links a + a { margin-left: .5rem; }
</style>

{% assign members = site.data.members %}

<div class="members-grid">
{% for m in members %}
  <div class="member-card">
    <img class="member-photo" src="{{ m.photo | default: '/images/members/default.png' | relative_url }}" alt="{{ m.name }}">
    <div class="member-name">{{ m.name }}</div>
    {% if m.role %}<div class="member-meta">{{ m.role }}</div>{% endif %}
    {% if m.affiliation %}<div class="member-meta">{{ m.affiliation }}</div>{% endif %}
    {% if m.program or m.start %}
      <div class="member-meta">
        {% if m.program %}{{ m.program }}{% endif %}
        {% if m.start %}{% if m.program %} · {% endif %}{{ m.start }}–{% endif %}
      </div>
    {% endif %}
    {% if m.tags %}<div class="member-tags"><em>{{ m.tags | join: ' · ' }}</em></div>{% endif %}
    <p class="member-links">
      {% if m.email %}<a href="mailto:{{ m.email }}">Email</a>{% endif %}
      {% if m.cv %}{% if m.email %} · {% endif %}<a href="{{ m.cv | relative_url }}">CV</a>{% endif %}
      {% if m.scholar %}{% if m.email or m.cv %} · {% endif %}<a href="{{ m.scholar }}">Scholar</a>{% endif %}
      {% if m.website %}{% if m.email or m.cv or m.scholar %} · {% endif %}<a href="{{ m.website }}">Website</a>{% endif %}
    </p>
  </div>
{% endfor %}
</div>

> To add a new member, edit `_data/members.yml` (add a new block) and upload their photo to `images/members/`.
