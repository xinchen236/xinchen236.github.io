---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---
{% include base_path %}


My research interests are in area of cyber-physical and energy systems, from the perspective of machine learning, optimization, and control. Here is a list of selective research projects that I have worked on. Click on the title link for more details!

{% for post in site.research %}
  {% include archive-single.html %}
{% endfor %}
