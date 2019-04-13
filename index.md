
	{% for art_change in site._data.art_change %}
	  {{ art_change.id }}
	  {{ art_change.title }}
	  {{ art_change.attribution }}
	{% endfor %}
