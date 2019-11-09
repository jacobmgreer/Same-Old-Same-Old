---
roomTitle: "East Building"
---

<table
  id="arttable"
  data-url="../../art_change.json"
  data-filter-control="true"
  data-show-search-clear-button="true">
	<thead>
		<tr>
			<th data-field="title">Artwork Title</th>
			<th data-field="attribution" data-filter-control="input">Attribution</th>
			<th data-field="roomTitle" data-filter-control="select">Location</th>
			<th data-field="Status" data-filter-control="select">Update</th>
		</tr>
	</thead>
</table>

<script>
  $(function() {
    $('#arttable').bootstrapTable()
  })
</script>