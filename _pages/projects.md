---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

Below are my main projects (contains unpublished contents therefore some are not in detail)


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.projects reversed %}
  {% include archive-single.html %}
{% endfor %}
