---
layout: default
title: Articles
---

{{ content }}

{% capture article_list %}
  {% include_relative _articles.md %}
{% endcapture %}
{{ article_list | markdownify }}
