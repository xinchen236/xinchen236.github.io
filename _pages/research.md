---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---
{% include base_path %}


My research interests lie in learning, optimization, and control of cyber-physical systems, with emphasis applications to power and energy systems.

{% for post in site.research %}
  {% include archive-single.html %}
{% endfor %}
