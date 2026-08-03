---
title: "Outreach"
permalink: /outreach/
author_profile: true
---

## Outreach & service

- **Member & designer**, KIPAC Communications Committee (2026)
- **Guest lecturer**, Stanford Program for Inspiring the Next Generation of Women in Physics (2026)
- **Interview panelist**, KIPAC communications associate search (2026)
- **Artist and science communication volunteer**, [KIPAC Research Highlights](https://kipac.stanford.edu/news/research-highlights-0) (2026)
- **Counselor**, Stanford Program for Inspiring the Next Generation of Women in Physics (2025)
- **Volunteer**, KIPAC High School Solar Physics Outreach (2025)
- **Booth leader & activity developer**, KIPAC Community Day dark matter booth (2025)
- **Volunteer**, Equity & Inclusion Panel, Stanford Physics, Identity, & Equity program (2024)
- **Volunteer**, KIPAC Community Day cosmic magnetism booth (2023)

## Photos

<style>
  .outreach-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
  }

  .outreach-gallery figure {
    margin: 0;
  }

  .outreach-gallery img {
    width: 100%;
    height: 260px;
    object-fit: cover;
  }

</style>

{% assign outreach_photo_count = 0 %}
{% for image in site.static_files %}
  {% if image.path contains '/images/outreach/' %}
    {% assign extension = image.extname | downcase %}
    {% if extension == '.jpg' or extension == '.jpeg' or extension == '.png' or extension == '.webp' or extension == '.gif' %}
      {% assign outreach_photo_count = outreach_photo_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}

{% if outreach_photo_count > 0 %}
<div class="outreach-gallery">
{% for image in site.static_files %}
  {% if image.path contains '/images/outreach/' %}
    {% assign extension = image.extname | downcase %}
    {% if extension == '.jpg' or extension == '.jpeg' or extension == '.png' or extension == '.webp' or extension == '.gif' %}
      <figure>
        <img src="{{ image.path | relative_url }}" alt="Outreach event photo">
      </figure>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
{% else %}
Photos from outreach events will be added here.
{% endif %}
