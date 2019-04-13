
<ul>
{% for art_change in site.data.art_change %}
  <li>{{ art_change.title }}</li>
  <li>{{ art_change.roomTitle }}</li>
  <li>{{ art_change.Status }}</li>
{% endfor %}
</ul>
