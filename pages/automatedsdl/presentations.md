---
layout: default
---
<ul>
  {% for slide in slides %}
  <li>
    <h1>
      <a href="{{ slide.url | prepend: site.baseurl | remove: 'index' }}">
        {{ slide.title }}
      </a>
    </h1>
    <p>{{ slide.date | date: }} - {{ slide.description }}</p>
  </li>
  {% endfor %}
</ul>
