<!-- this component returns a list of all the buildings -->
<template>
    <div class="container.xxl events m-5">
	<div class="">
		<!-- these would show while the data loads or if an error -->
		<p v-if="$fetchState.pending">Loading events...</p>
		<p v-else-if="$fetchState.error">Error while fetching events</p>

		<ul v-else class="list-group">
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="events in events" :key="events.id" class="list-group-item blue">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="events.slug"> -->
				<NuxtLink :to="'/events/' + events.slug">
					<!-- return the rendered title -->
					{{  events.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ events.acf.year }}
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
// Components JS Scripts would go here

export default {
	// layout: 'home',
	async fetch() {
		this.events = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100').then((res) =>
			res.json()
		)
	},
	data() {
		return {
			events: [],
		}
	},
}
</script>