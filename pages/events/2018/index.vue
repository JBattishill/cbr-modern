<template>
	<div class="container">
		<h2>All events</h2>
		<h3>Filename: pages/events/2017/index.vue</h3>

		<SiteNavigation />

		<ul class="list-group">
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="building in buildings" :key="building.id" class="list-group-item">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="building.slug"> -->
				<NuxtLink :to="'/buildings/' + building.slug">
					<!-- return the rendered title -->
					{{  building.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ building.acf.year }}
			</li>
		</ul>

		<h3>this list is stored in components/BuildingsList.vue</h3>
		<!-- <div class="events">
			<h1>This is the 2018 events page</h1>
			<EventsNav />
			
		</div> -->
	</div>
</template>

<script>

// in this API call, we go get a specific building, filtered by the ID in the URL
// we access what is in the URL by using the params object

export default {
	async asyncData({ params }) {
		const events = await fetch(
			`http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100`
		).then((res) => {
			if (res.ok) {
		// console.log(res)
				return res.json()
			}
			throw new Error(res.status)
		})
		// Filtering data to show only 2018 events
		// create empty araay
		let yearArr = [];
		//loop through buildings/events array
			for (let i = 0; i < events.length; i++) {
				// some variables
				let year = "2018";
				let eventYear = events[i].acf.year;
				// for each one, check the year
					if (eventYear == year) {
						//if there's a match, push into new array
							yearArr.push(events[i]);
					}
			}
			// console printing new array
		console.log(yearArr);
		return { yearArr }
	},
}
</script>