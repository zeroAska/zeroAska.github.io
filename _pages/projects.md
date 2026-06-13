---
layout: page
title: Projects
permalink: /projects/
description: 
nav: true
nav_order: 2
home_anchor: projects
display_categories: 
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
  {% include project_list.html projects=sorted_projects %}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  {% include project_list.html projects=sorted_projects %}
{%- endif -%}
</div>
