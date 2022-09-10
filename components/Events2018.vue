<!-- this component returns a list of all the buildings by year -->
<template>
	<div class="">
		<!-- these would show while the data loads or if an error -->
		<p v-if="$fetchState.pending"> <span class="loading"></span></p>
		<p v-else-if="$fetchState.error">Error while fetching events</p>

		<ul v-else class="list-group">
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="event in events" :key="event.id" class="list-group-item">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="building.slug"> -->
				<NuxtLink :to="'/events/' + event.slug">
					<!-- return the rendered title -->
					{{  event.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ event.acf.year }}
			</li>
		</ul>

	</div>
</template>


<script>
//original - works
// export default {
// 	// layout: 'home',
// 	async fetch() {
// 		this.buildings = await fetch('http://cm.beneb.com/wp-json/wp/v2/buildings/?per_page=20').then((res) =>
// 			res.json()
// 		)
// 	},
// 	data() {
// 		return {
// 			buildings: [],
// 		}
// 	},
// }
export default {
	//data will return an array
	data() {
		return {
			//empty array to be filled
			events: [],
		}
	},
	//now go get the data
	async fetch() {
		//make the api call and fill the empty buildings array
		let apiData = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100')
		.then((response) =>
			response.json()
		)
		// // create empty araay
		let yearArr = [];
		//loop through buildings/events array
		for (let i = 0; i < apiData.length; i++) {
			// some variables
			let year = "2018";
			let eventYear = apiData[i].acf.year;
			// for each one, check the year
				if (eventYear == year) {
					//if there's a match, push into new array
						yearArr.push(apiData[i]);
				}
		} 
		//now set buildings to be the yearArray 
		this.events = yearArr;
	},
	
	
}
</script>