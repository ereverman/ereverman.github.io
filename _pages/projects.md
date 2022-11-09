---
layout: page
title: Genetic dissection of metal resistance
permalink: /projects/
description: The Goal: We are currently characterizing the genetic factors that influence copper resistance as a part of a broader goal to understand the genetic control of physiological and behavioral responses to heavy metal pollution.

The Rationale: Metal pollution is a ubiquitous and persistent threat to human and environmental health. Copper is a common pollutant and is an excellent “model metal” for studying heavy metal stress response: many of the genes that metabolize and detoxify copper also interact with non-essential heavy metals (e.g. lead and cadmium). Our work has demonstrated that copper resistance is phenotypically correlated with resistance to other metals (lead, cadmium, and others), with evidence of overlap in the genetic control of these resistance traits.
​
The Questions:
What is the genetic basis of copper resistance?
Do genetic factors that influence copper resistance have life stage-specific effects?
Is the physiological response to copper influenced by behavioral responses to copper stress?
What genetic factors influence the dynamic shift in gene expression in response to copper stress?
Does copper resistance vary in natural populations in response to pollution resulting from mining activities?
​
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
