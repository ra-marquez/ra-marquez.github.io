---
layout: page
title: Research
permalink: /research/
description: These projects represent my research interests and the focus of my career efforts.   
nav: true
nav_order: 2
display_categories: [Electrocatalysis, Methods in Electrochemistry, Sustainable Processes, Electrochemical Engineering]
horizontal: false
---

My goal is to develop sustainable solutions for challenges in <strong>renewable energy</strong>, <strong>water resources</strong>, and the <strong>chemical industry</strong>. To achieve these goals, I incorporate principles of <strong>electrochemistry</strong>, <strong>catalysis</strong>, <strong>analytical chemistry</strong>, and <strong>chemical engineering</strong> into my research. This work encompasses a range of scales, from understanding <strong>catalytic interfaces</strong> at the atomic level to <strong>chemical processes</strong> (<strong>Figure 1</strong>).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Scales.png" title="flowcell" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. The length scales of my research interests span from catalytic surface to device integration and engineering.
</div>


<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
