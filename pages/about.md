---
layout: page
title: About
permalink: /about/
---

FileFighter fights against chaos in your home-Nas.
We provide a stable and clearly structured web application, to upload, download and manage your files.

FileFighter is developed by:  
{% for author in site.authors %}
  <h2>{{ author.name }} - {{ author.position }}</h2>
  <p><small><a href="{{ author.github }}">Github</a></small></p>
  <p>{{ author.content | markdownify }}</p>
{% endfor %}