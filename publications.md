---
layout: page
title: Publications
permalink: /publications/
nav: true
nav_order: 2
---

{% assign groups = site.data.publications | group_by: 'year' %}
{% for group in groups %}

## {{ group.name }}

{% for paper in group.items %}
**{{ paper.title }}**  
{{ paper.authors }}  
_{{ paper.venue }}_  
{{ paper.type }}{% if paper.url != '' %} · [{{ paper.link_label }}]({{ paper.url }}){% endif %}

{% endfor %}
{% endfor %}
