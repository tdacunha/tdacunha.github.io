---
title: "Astro Illustrations"
permalink: /portfolio/
author_profile: true
---

I create digital illustrations for astronomy research and science communication.

<style>
  .illustration-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
  }

  .illustration-gallery figure {
    margin: 0;
  }

  .illustration-gallery img {
    width: 100%;
    height: 260px;
    object-fit: contain;
  }

  .illustration-gallery figcaption {
    margin-top: 0.5rem;
    text-align: center;
  }
</style>

<div class="illustration-gallery">
{% for image in site.static_files %}
  {% if image.path contains '/images/astro-illustrations/' %}
    {% assign extension = image.extname | downcase %}
    {% if extension == '.jpg' or extension == '.jpeg' or extension == '.png' or extension == '.webp' or extension == '.gif' %}
      {% assign illustration_title = image.basename | replace: '_', ' ' | replace: '-', ' ' %}
      <figure>
        <img src="{{ image.path | relative_url }}" alt="{{ illustration_title }}">
        <figcaption>{{ illustration_title }}</figcaption>
      </figure>
    {% endif %}
  {% endif %}
{% endfor %}
</div>
