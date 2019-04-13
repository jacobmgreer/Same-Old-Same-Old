{% for art_change in site._data.art_change %}
<li>{{ art_change.title }}</li>
<li>{{ art_change.attribution }}</li>
<li>{{ art_change.roomTitle }}</li>
<li>{{ art_change.Status }}</li>
{% endfor %}
