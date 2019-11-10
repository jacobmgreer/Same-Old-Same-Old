---
roomTitle: "East Building"
title: "East Building"
---

<table id="artTable" class="table">
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

<style>
#artTable tbody td img {width:50px; dispay:none;}
.feather {
  width: 16px;
  height: 16px;
  vertical-align: text-bottom;
}
</style>




<script>
//$('#monthdrop').click(function(){
//	$('#monthdrop .dropdown-menu').toggleClass('show');
//});

$(document).ready(function(){
	$.getJSON('https://jacobmgreer.github.io/Same-Old-Same-Old/art_change.json', 
		function(data) {
			var month_name = [];
			data.forEach(function(obj) {
				if(month_name.indexOf(obj.month) == -1)
				   month_name.push(obj.month);
				var lastIndex = month_name.length - 1;
			});

			for (month in month_name) {
				$(".month-menu").append(
					"<li><a class=\"dropdown-item\" href=\"#\">" + month_name[month] + "</a></li>");}
			for (record in data) {
				$("#artTable tbody").append(
					"<tr> \
					    <td height=\"100\"> \
					    	<img src=\"" + data[record].imagepath + "\" onload=\"this.style.display=''\"/></td> \
						<td><a href=\"https://www.nga.gov" + data[record].url + "\">" + data[record].title + "</a></td> \
						<td>" + data[record].attribution + "</td> \
						<td>" + data[record].roomTitle + "</td> \
						<td class=\"text-dark\"><span data-feather=\"" + (data[record].Status == "Added" ? "plus-circle" : "minus-circle") + "\"></span> status</td> \
						<td>" + data[record].datechange + "</td> \
				    </tr>");}})})
feather.replace();
</script>