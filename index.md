---
title: Same Old Same Old
layout: default
---

<table id="artTable" class="table table-hover table-responsive">
	<thead>
	    <tr>
	      <th scope="col"></th>
	      <th scope="col"></th>
	      <th scope="col">Artwork Title</th>
	      <th scope="col">Attribution</th>
	      <th scope="col" style="width:30%">Room</th>
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
// $('#month-menu-button').click(function(){$('#month-menu').toggleClass('show');});

$(document).ready(function(){
	$.getJSON('https://jacobmgreer.github.io/Same-Old-Same-Old/art_change.json', function(data) {
		var month_name = [];
		var data3 = data.slice(0, 25);

		data.forEach(function(obj) {
			if(month_name.indexOf(obj.monthyear) == -1)
			   month_name.push(obj.monthyear);
			var lastIndex = month_name.length - 1;
		});
		for (month in month_name) {
			$("#month-menu").append(
				"<li><a class=\"dropdown-item month-item\" data-month=\"" + month_name[month] + "\" href=\"#\">" + month_name[month] + "</a></li>")}


		for (record in data3) {
			$("#artTable tbody").append(
				"<tr> \
					<td>" + (data3[record].Status == "Added" ? "+" : "-") + "</td> \
				    <td height=\"100\"> \
				    	<img src=\"" + data3[record].imagepath + "\" width=\"50\" style=\"display: none\" onerror=\"this.style.display='none'\" onload=\"this.style.display=''\"/></td> \
					<td><a href=\"https://www.nga.gov" + data3[record].url + "\">" + data3[record].title + "</a></td> \
					<td>" + data3[record].attribution + "</td> \
					<td>" + data3[record].roomTitle + "</td> \
			    </tr>")}
    $('.month-item').each(function () {
        $(this).on("click", function () {
        	$("#artTable tbody").empty();
        	var clickmonth = $(this).data("month");
          var data2 = data.filter(element => element.month === clickmonth);
          for (var i in data2) {
            $("#artTable tbody").append(
              "<tr> \
                <td>" + (data2[i].Status == "Added" ? "+" : "-") + "</td> \
                <td height=\"100\"> \
                <img src=\"" + data2[i].imagepath + "\" width=\"50\" style=\"display: none\" onerror=\"this.style.display='none'\" onload=\"this.style.display=''\"/></td> \
                <td><a href=\"https://www.nga.gov" + data2[i].url + "\">" + data2[i].title + "</a></td> \
                <td>" + data2[i].attribution + "</td> \
                <td>" + data2[i].roomTitle + "</td> \
              </tr>"
)}})})})})

feather.replace();

// <td class=\"text-dark\"><span data-feather=\"" + (data[record].Status == "Added" ? "plus-circle" : "minus-circle") + "\"></span> status</td> \
</script>