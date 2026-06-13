---
layout: page
permalink: /repositories/
title: Code
description: Selected Public Repos
nav: true
nav_order: 3
home_anchor: code
---

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
