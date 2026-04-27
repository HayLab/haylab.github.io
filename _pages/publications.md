---
layout: page
permalink: /publications/
title: publications
priority: 3
description: Publications by categories in reversed chronological order. * represents co-first authors, ** represents co-corresponding authors.
years: [2026, 2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2004, 2003, 2002, 2001, 2000, 1999, 1997, 1995, 1994, 1992, 1990, 1988, 1987, 1984]
nav: true
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
