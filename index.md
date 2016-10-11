---
layout: default
---

# https://dvon.github.io/ccsc-tutorial/

{% assign sorted_pages = site.pages | sort: 'section' %}
{% for page in sorted_pages %}
{% if page.section != null %}

<a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a>:
<span markdown="1">{{ page.summary }}</span>

{% endif %}
{% endfor %}
