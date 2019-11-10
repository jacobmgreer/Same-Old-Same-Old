---
roomTitle: "East Building"
---

<table id="artTable">
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
  	<tbody></tbody>
</table>

<script>
$(document).ready(function(){
	$.getJSON('https://jacobmgreer.github.io/Same-Old-Same-Old/art_change.json', 
		function(data) {for (record in data) {
			$("#artTable tbody").append(
				"<tr> \
				    <td>" + data[record].imagepath + "</td> \
					<td>" + data[record].title + "</td> \
					<td>" + data[record].attribution + "</td> \
					<td>" + data[record].roomTitle + "</td> \
					<td>" + data[record].Status + "</td> \
					<td>" + data[record].datechange + "</td> \
			    </tr>");}})})
</script>