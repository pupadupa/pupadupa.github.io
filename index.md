---
layout: default
title: Poor Konstantin's Almanac
---

A collection of observations, principles, and mental models — shaped by product thinking, grounded in real-world execution, and sharpened by hard lessons. Not a playbook. Not a manifesto. Just things worth writing down — so I don’t forget them, and maybe you won’t either.

{% capture article_list %}
  {% include_relative articles/_articles.md %}
{% endcapture %}
{{ article_list | markdownify }}
