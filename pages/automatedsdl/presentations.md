---
layout: slides
title: Jekyll and reveal.js
description: A presentation slide for how to use reveal.js in Jekyll
theme: white
transition: slide
permalink: presentations.html
---


{% for slide in site.slides %}
<section>
    {{ slide.content }}
</section>
{% endfor %}
