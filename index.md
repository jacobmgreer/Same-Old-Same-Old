<ul>
{% for art_change in site.data.art_change %}
  <li>
      {{ art_change.title }}
  </li>
{% endfor %}
</ul>
