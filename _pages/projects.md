---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

Here are the projects I've worked on during grad school.

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
