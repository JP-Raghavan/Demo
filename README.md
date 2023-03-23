<!DOCTYPE html>
<html>
<head>
	<title>My Dashboard</title>
	<style>
		.container {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			grid-gap: 20px;
		}
		.item {
			background-color: #f2f2f2;
			padding: 20px;
			border-radius: 5px;
			box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
			text-align: center;
		}
		.item:hover {
			cursor: pointer;
			background-color: #ddd;
		}
		.item.active {
			background-color: #00c853;
			color: #fff;
			box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
		}
	</style>
	<script src="https://statics.teams.cdn.office.net/sdk/v1.8.0/js/MicrosoftTeams.min.js"></script>
	<script>
		function toggleActive(item) {
			// Get the Teams user information
			microsoftTeams.getContext(function(context) {
				// Update the item's text content to include the user's name
				item.textContent = `Item ${item.dataset.itemId} - User: ${context.userDisplayName}`;
			});

			// Toggle the item's active class
			item.classList.toggle("active");
		}
	</script>
</head>
<body>
	<div class="container">
		<div class="item" onclick="toggleActive(this)" data-item-id="1">Item 1</div>
		<div class="item" onclick="toggleActive(this)" data-item-id="2">Item 2</div>
		<div class="item" onclick="toggleActive(this)" data-item-id="3">Item 3</div>
		<div class="item" onclick="toggleActive(this)" data-item-id="4">Item 4</div>
	</div>
</body>
</html>
