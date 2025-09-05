---
layout: default
title: "Currículo"
---

<header class="hero">
  <img class="avatar" src="{{ site.author.avatar_url }}" alt="{{ site.author.name }}">
  <h1>{{ site.author.name }}</h1>
  <p class="role">{{ site.author.role }}</p>
  <p class="desc">{{ site.description }}</p>
</header>

## Habilidades
<ul class="chips">
{% for s in site.data.skills %}
  <li>{{ s }}</li>
{% endfor %}
</ul>

## Contato
<div class="socials">
{% for s in site.data.socials %}
  <a class="btn" href="{{ s.url }}" target="_blank" rel="noopener">{{ s.label }}</a>
{% endfor %}
</div>

## Projetos
<div class="cards">
  {% assign items = site.projects | sort: 'title' %}
  {% for p in items %}
    <a class="card" href="{{ p.url | relative_url }}">
      <h3>{{ p.title }}</h3>
      <p>{{ p.excerpt | default: p.content | strip_html | truncate: 120 }}</p>
    </a>
  {% endfor %}
</div>
