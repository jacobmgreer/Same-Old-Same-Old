<style>
td {font-size:11px;}
</style>

<table>
{% for art_change in site.data.art_change %}
  <tr>
  	<td height="100"><img src="{{ art_change.imagepath }}" width="50"/></td>
    <td><a href="https://www.nga.gov{{ art_change.url }}">{{ art_change.title }}</a></td>
    <td>{{ art_change.roomTitle }}</td>
    <td>{{ art_change.Status }}</td>
  </tr>
{% endfor %}
</table>
