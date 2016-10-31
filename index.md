---
layout: default
---

# https://dvon.github.io/ccsc-tutorial/

This tutorial was prepared for the [CCSC Eastern](http://www.ccsc-eastern.org)
fall 2016 regional conference, with the title "Using GitHub Pages for a
Computer Science Course Website."

{% assign sorted_pages = site.pages | sort: 'section' %}
{% for page in sorted_pages %}
{% if page.section != null %}

<a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a>:
<span markdown="1">{{ page.summary }}</span>

{% endif %}
{% endfor %}
