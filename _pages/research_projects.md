---
layout: page
%title: research
permalink: /projects/
description: Some of my recent sensorimotor research projects within bioastronautics
nav: true
nav_order: 3
display_categories: [modeling perception, motion sickness, galvanic vestibular stimulation, NASA experience]
horizontal: false
---

One pillar of my research focuses on understanding sensory processing. In part, I have focused on improving mathematical models of sensory processing during periods of central adaptation, necessary for modeling central perceptual function following gravity transitions. Such models seek to quantify three aspect about humans' internal representations of self motion and self orientation by predicting how a person will perceive: <b>In what way am I moving/oriented? Which way am I moving/oriented? How much am I moving/have I moved? <b> In other words, we seek to model perceptions of <b>motion type, direction, and magnitude.<b> Designing and performing human participant experiments that empirical assesses these aspects of perception allows us to built models that can predict a variety of outcomes such as: misperceptions in altered gravity environments, locomotion performance and manual control during landing, and even the development of motion sickness symptoms.

Motion sickness, thought to be a consequence of neurovestibular processing, pervades all modes of human transportation (e.g., automobiles, boats, trains, airplanes, spaceflight). Most astronauts experience motion sickness upon transitioning to a microgravity environment from Earth and upon returning to Earth following extended exposure to microgravity. During my doctoral thesis, I constructed a predictive model of motion sickness resulting from arbitrary motion paradigms and changing gravity environments. In addtion, my research has empirically assessed motion sickness countermeasures for re-entry using gravity transition and sea-state paradigms. These countermeasures were developed using virtual reality environments, varying levels of postural control and predictive cueing displays.

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
