<template>
	<div class="">
		<!-- Component for Navigation -->
		<SiteNavigation />
		<div class="content">
			<BuildingsList />
		</div>
	</div>
</template>

<script>
// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	async asyncData({ params }) {
		const building = await fetch(
			`http://cm.beneb.com/wp-json/wp/v2/buildings/`
		).then((res) => {
			if (res.ok) {
				return res.json()
			}
			throw new Error(res.status)
		})
		console.log(building);
		// create empty araay
		let yearArr = [];
		//loop through buildings/events array
			for (let i = 0; i < building.length; i++) {
				// some variables
				let year = "1971";
				let buildingYear = building[i].acf.year;
				// for each one, check the year
					if (buildingYear == year) {
						//if there's a match, push into new array
							yearArr.push(building[i]);
					}
			}
			console.log(yearArr);
		return { building }
	},
}
</script>


<style>
</style>