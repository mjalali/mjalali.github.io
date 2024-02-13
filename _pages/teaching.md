---
layout: page
permalink: /teaching/
title: teaching
description: Materials for courses I taught during my bachelors at the Isfahan University of Technology!
nav: true
nav_order: 5
---

### Teaching assistant at Isfahan University of Technology

This repository contains the homework and projects I developed during my tenure as a teaching assistant at the IUT. Please feel free to peruse through the repository and reach out to me in case you require any clarifications.

{% if site.data.repositories.teaching_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.teaching_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
