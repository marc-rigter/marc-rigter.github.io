---
layout: about
title: About
permalink: /
subtitle: Researcher in AI and machine learning.

profile:
  align: left
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: 

news: true # includes a list of news items
latest_posts: false # includes a list of the newest posts
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page
---

Welcome to my personal website!

I'm currently a machine learning researcher in the [Causica team at Microsoft Research](https://www.microsoft.com/en-us/research/project/project_azua/people/), working on improving the decision-making capabilities of foundation models.

Previously I was a postdoc at the [Applied AI Lab](https://ori.ox.ac.uk/labs/a2i/) at the [Oxford Robotics Institute](https://ori.ox.ac.uk/) (ORI) at the University of Oxford. I completed my PhD in Information Engineering at the [GOALS Group](https://ori.ox.ac.uk/labs/goals/) also at the ORI. At Oxford, my research focused on generative "world" models, model-based reinforcement learning, and planning under uncertainty.

Please feel free to reach out if you would like to chat about anything!

&nbsp;
&nbsp;

## Photo Collections

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
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
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
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

&nbsp;
&nbsp;
