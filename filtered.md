---
title: Same Old Same Old | Filtered
path: gallery/:Path
layout: default
---

<table class="table">
	<thead>
	    <tr>
	      <th scope="col">Image</th>
	      <th scope="col">Artwork Title</th>
	      <th scope="col">Attribution</th>
	      <th scope="col">Location</th>
	      <th scope="col">Update</th>
	      <th scope="col">Changed</th>
	    </tr>
  	</thead>
  	<tbody>
  		{% assign art = site.data.art_change | where_exp: "item", "item.roomTitle contains 'West Building'" | where: "Status", "Added" %}
		{% for art_change in art %}
		  <tr>
		  	<td height="100"><img src="{{ art_change.imagepath }}" width="50" style="display: none" onload="this.style.display=''"/></td>
		    <td><a href="https://www.nga.gov{{ art_change.url }}">{{ art_change.title }}</a></td>
		    <td>{{ art_change.attribution }}</td>
		    <td>{{ art_change.roomTitle }}</td>
		    <td>{{ art_change.Status }}</td>
		    <td>{{ art_change.datechange }}</td>
		  </tr>
		{% endfor %}
	</tbody>
</table>
