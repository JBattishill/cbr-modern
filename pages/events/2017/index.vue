<template>
	<div class="container">
		<h2>All events</h2>
		<h3>Filename: pages/events/2017/index.vue</h3>

		<SiteNavigation />


		<div class="events">
			<h1>This is the 2017 events page</h1>
			<EventsNav />
			<!-- The building list is over in the components folder -->
			<!-- the code below loads the component here so we can use it again -->
			<Events2017 />

			<!-- this is a really useful line of code that will just output what the API call returns -->
			<!-- <pre>{{ $data }}</pre> -->
		</div>
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
		// Filtering data to show only 2017 events
		// create empty araay
		let yearArr = [];
		//loop through buildings/events array
			for (let i = 0; i < events.length; i++) {
				// some variables
				let year = "2017";
				let eventYear = events[i].acf.year;
				// for each one, check the year
					if (eventYear == year) {
						//if there's a match, push into new array
							yearArr.push(events[i]);
					}
			}
			// console printing new array
		//	console.log(yearArr);
		return { yearArr }
	},
}
</script>