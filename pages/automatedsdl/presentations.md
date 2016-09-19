---
layout: default
permalink: presentations.html
---

<div id="home">
  <h1>Presentations:</h1>
  <ul>
    {% for slide in site.slides %}
    <li>
      <a class="slide-entry" href="{{ slide.url }}">{{ slide.title }}</a>
      <small>{{ slide.description }}</small>
    </li>
    {% endfor %}
  </ul>
</div>
