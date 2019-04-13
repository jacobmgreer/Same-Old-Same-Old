
<ul>
{% for art_change in site.data.art_change %}
  <li>{{ art_change.title }}: {{ art_change.roomTitle }}</li>
{% endfor %}
</ul>
