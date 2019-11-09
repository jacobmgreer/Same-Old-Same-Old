---
roomTitle: "East Building"
---

<table id="table" class="table" data-filter-control="true">
	<thead>
	    <tr>
	      <th data-field="Image" scope="col">Image</th>
	      <th data-field="Artwork Title" scope="col">Artwork Title</th>
	      <th data-field="Attribution" scope="col" data-filter-control="input">Attribution</th>
	      <th data-field="Location" scope="col" data-filter-control="select">Location</th>
	      <th data-field="Update" scope="col" data-filter-control="select">Update</th>
	      <th data-field="Changed" scope="col">Changed</th>
	    </tr>
  	</thead>
  	<tbody>
  		{%  
			assign art = site.data.art_change | 
			where_exp: "item", "item.roomTitle contains page.roomTitle" | 
			where: "Status", "Added" 
  		%}
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
