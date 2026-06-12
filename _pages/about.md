---
layout: about
permalink: /
title: about
priority: 1

profile:
  align: right
  image: Kerckhoff_front.jpg

News: true  # includes a list of news items
          {% if page.news -%}
          <!-- News -->
          {%- include news.html %}
          {%- endif %}
social: false  # includes social icons at the bottom of the page
---

Welcome to the Bruce Hay Lab website!

Our lab is interested in modifying genomes, from individual cells to whole organisms to whole populations. Some specific examples include modifying mitochondrial quality in animals and plants, one-off contraceptive shots for animals, and the development of various gene drives for the modification or removal or pest species. <br>
For more information about specific projects, please visit our projects page.
