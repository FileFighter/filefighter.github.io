---
layout: page
title: About
permalink: /about/
---

FileFighter is developed by:  
{% for author in site.authors %}
  <h2>{{ author.name }} - {{ author.position }} <a href="{{ author.github }}" target="_blank"><img alt="githublogo" src="https://github.githubassets.com/favicons/favicon-dark.png" width="32" height="32" /></a></h2>
  <p>{{ author.content | markdownify }}</p>
{% endfor %}