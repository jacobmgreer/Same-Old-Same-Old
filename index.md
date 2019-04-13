<table>
{% for art_change in site._data.art_change %}
  <tr>
      <td>{{ art_change.id }}</td>
      <td>{{ art_change.title }}</td>
      <td>{{ art_change.attribution }}</td>
      <td>{{ art_change.roomTitle }}</td>
      <td>{{ art_change.Status }}</td>
  </tr>
{% endfor %}
</table>
