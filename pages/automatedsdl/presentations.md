---
layout: slides
title: Jekyll and reveal.js
description: A presentation slide for how to use reveal.js in Jekyll
permalink: presentations.html
theme: white
transition: slide
---


{% for slide in site.slides %}
<section>
    {{ slide.content }}
</section>
{% endfor %}


