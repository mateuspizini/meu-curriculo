---
layout: home
title: "Currículo"
---

> Olá! Sou o **{{ site.author.name }}**, {{ site.author.role }}.  
Tenho experiência com **Python, C#, C++, HTML, CSS, JavaScript, React** e consumo de **APIs REST**.

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

## Currículo

<div class="accordion" markdown="1">

### Educação
{% for ed in site.data.resume.education %}
<details class="acc">
  <summary>
    <span class="acc-title">{{ ed.course }}</span>
    <span class="acc-meta">{{ ed.school }} · {{ ed.location }} · {{ ed.start }}–{{ ed.end }}</span>
  </summary>
  <div class="acc-body">
    {% if ed.highlights %}<ul>
      {% for h in ed.highlights %}<li>{{ h }}</li>{% endfor %}
    </ul>{% endif %}
  </div>
</details>
{% endfor %}

### Experiência
{% for job in site.data.resume.experience %}
<details class="acc">
  <summary>
    <span class="acc-title">{{ job.role }} — {{ job.company }}</span>
    <span class="acc-meta">{{ job.location }} · {{ job.start }}–{{ job.end }}</span>
  </summary>
  <div class="acc-body">
    {% if job.description %}<p>{{ job.description }}</p>{% endif %}
    {% if job.highlights %}<ul>
      {% for h in job.highlights %}<li>{{ h }}</li>{% endfor %}
    </ul>{% endif %}
  </div>
</details>
{% endfor %}

{% if site.data.resume.certifications %}
### Certificações
{% for c in site.data.resume.certifications %}
<details class="acc">
  <summary>
    <span class="acc-title">{{ c.name }}</span>
    <span class="acc-meta">{{ c.org }} · {{ c.year }}</span>
  </summary>
</details>
{% endfor %}
{% endif %}

{% if site.data.resume.languages %}
### Idiomas
<details class="acc">
  <summary>
    <span class="acc-title">Idiomas</span>
    <span class="acc-meta">{{ site.data.resume.languages | join: " · " }}</span>
  </summary>
</details>
{% endif %}

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
{% endif %}
