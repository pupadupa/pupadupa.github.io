---
layout: default
title: For Kids
---

A short list of sites worth a kid's time — ages 9 to 13 roughly. The rule for
what gets added here: you have to *read and do*, not just watch. Coding,
science experiments, 3D design, building instructions — real projects with
real steps, not a video to sit through.

<div class="kids-resources">
{% for resource in site.data.kids_resources %}
  <section class="kids-resource">
    <h2 class="kids-resource-headline">
      <a href="{{ resource.url }}" target="_blank" rel="noopener">{{ resource.name }}</a>
    </h2>
    <p class="kids-resource-tagline">{{ resource.tagline }}</p>
    <p class="kids-resource-desc">{{ resource.description }}</p>

    <div class="kids-project-grid">
      {% for project in resource.projects %}
        <a class="kids-project-card" href="{{ project.url }}" target="_blank" rel="noopener">
          <span class="kids-project-title">{{ project.title }}</span>
          <span class="kids-project-desc">{{ project.description }}</span>
        </a>
      {% endfor %}

      <a class="kids-project-card kids-other-card" href="{{ resource.other.url }}" target="_blank" rel="noopener">
        <span class="kids-project-title">{{ resource.other.label }} &rarr;</span>
      </a>
    </div>
  </section>
{% endfor %}
</div>
