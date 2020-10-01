---
layout: page
title: About
permalink: /about/
---

FileFighter fights against chaos in your home-Nas.
We provide a stable and clearly structured web application, to upload, download and manage your files.

FileFighter is developed by:  
{% for author in site.authors %}
  <h2>{{ author.name }} - {{ author.position }} <a href="{{ author.github }}"><img alt="githublogo" src="https://github.githubassets.com/favicons/favicon-dark.png" width="32" height="32"></img></a></h2>
  <p>{{ author.content | markdownify }}</p>
{% endfor %}