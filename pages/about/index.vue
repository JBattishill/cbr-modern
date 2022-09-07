<template>
	<div class="container">
		<h2>All events</h2>
		<h3>Filename: pages/about/index.vue</h3>

		<SiteNavigation />


		<div class="events">
			<h1>This is the About page</h1>
			<!-- The building list is over in the components folder -->
			<!-- the code below loads the component here so we can use it again -->

			<!-- this is a really useful line of code that will just output what the API call returns -->
			<!-- <pre>{{ $data }}</pre> -->
		</div>
	</div>
</template>

<script>
// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	// layout: 'home',
	async fetch() {
		this.buildings = await fetch('http://cm.beneb.com/wp-json/wp/v2/buildings/?per_page=20').then((res) =>
			res.json()
		)
	},
	data() {
		return {
			buildings: [],
		}
	},
}
</script>
