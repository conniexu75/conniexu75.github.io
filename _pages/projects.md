---
layout: page
title: Research
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

## Job Market Paper

**Squeezed at the Bench: Input Price Shocks and the Production of Science**
(with [Ruby Zhang](https://example.com/))

## Working Papers

**Place Effects on Scientific Productivity: Evidence from Researcher Moves**
(with [Amitabh Chandra](https://www.hks.harvard.edu/faculty/amitabh-chandra))

[One-paragraph abstract here.]

## Work in Progress

**The Ripple Effects of Health Care Entry Regulation**
(with [Parker Rogers](https://sites.google.com/site/parkerrogersecon) and [Yunan Ji](https://www.yunanji.com/))

[Abstract here.]

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
