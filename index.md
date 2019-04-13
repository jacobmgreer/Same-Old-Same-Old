<table>
	{% for art_change in site._data.art_change %}
	  <tr>
	      <td>{{ art_change.id }}</td>
	      <td>{{ art_change.title }}</td>
	  </tr>
	{% endfor %}
</table>
