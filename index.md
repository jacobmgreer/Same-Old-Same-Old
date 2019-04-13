<style>
td {font-size:11px;}
</style>

<table>
{% for art_change in site.data.art_change %}
  <tr>
    <td>{{ art_change.title }}</td><td>{{ art_change.roomTitle }}</td>
  </tr>
{% endfor %}
</table>
