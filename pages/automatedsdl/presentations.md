---
layout: default
permalink: presentations.html
---


{% for slide in site.slides %}
<section>
    {{ slide.content }}
</section>
{% endfor %}
