---
layout: home
title: "Currículo"
---

> Olá! Sou **{{ site.author.name }}**, {{ site.author.role }}.  
Tenho experiência com **C#, C++, Python, HTML, CSS, JavaScript, React** e consumo de **APIs REST**.

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

{% if site.projects and site.projects.size > 0 %}
## Projetos
<div class="cards">
  {% for p in site.projects %}
  <a class="card" href="{{ p.url | relative_url }}">
    <h3>{{ p.title }}</h3>
    <p>{{ p.excerpt | strip_html | truncate: 120 }}</p>
  </a>
  {% endfor %}
</div>

{% if items.size == 0 %}
<p>Nenhum projeto publicado ainda.</p>
{% endif %}
