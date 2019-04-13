<table>
{% for art_change in site._data.art_change %}
  <tr>
    <td>{{ art_change.title }}</td>
    <td>{{ art_change.attribution }}</td>
  </tr>
{% endfor %}
</div>
