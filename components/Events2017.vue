<!-- this component returns a list of all the buildings -->
<template>
    <div class="container.xxl events m-5">
	<div class="">
		<!-- these would show while the data loads or if an error -->
		<p v-if="$fetchState.pending">Loading events...</p>
		<p v-else-if="$fetchState.error">Error while fetching events</p>

		<ul v-else class="list-group">
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="yearArr in $data.info" v-bind:key="$data.info.yearArr.id" class="list-group-item blue">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="events.slug"> -->
				<NuxtLink :to="'/events/' + yearArr.slug">
					<!-- return the rendered title -->
					{{  yearArr.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ yearArr.acf.year }}
			</li>
		</ul>
		<h3>this list is stored in components/EventsList.vue</h3>
    </div>
	</div>
</template>

<style scoped>
    @import url('~assets/css/style.css');
</style>

<script>
export default {
	// layout: 'home',
	data: () => ({
    info: []
  }),

	async fetch() {
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
		// console.log(yearArr);
		return { yearArr }
		
	},
}
</script> 

<!-- 		
// 		this.events = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100').then((res) =>
// 			res.json()
// 		)
// 	},
// 	data() {
// 		return {
// 			events: [],
// 		}
// 	},
// }
// export default {
// 	async asyncData({ params }) {
// 		const events = await fetch(
// 			`http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100`
// 		).then((res) => {
// 			if (res.ok) {
// 		// console.log(res)
// 				return res.json()
// 			}
// 			throw new Error(res.status)
// 		})
// 		// Filtering data to show only 2017 events
// 		// create empty araay
// 		let yearArr = [];
// 		//loop through buildings/events array
// 			for (let i = 0; i < events.length; i++) {
// 				// some variables
// 				let year = "2017";
// 				let eventYear = events[i].acf.year;
// 				// for each one, check the year
// 					if (eventYear == year) {
// 						//if there's a match, push into new array
// 							yearArr.push(events[i]);
// 					}
// 			}
// 			// console printing new array
// 		//	console.log(yearArr);
// 		return { yearArr }
// 	},
// }
// </script>