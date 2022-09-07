<template>
	<div class="">
		<div>
			<!-- these would show while the data loads or if an error -->
			<p v-if="$fetchState.pending">Loading buildings...</p>
			<p v-else-if="$fetchState.error">Error while fetching buildings</p>
			<pre>{{ $data.about.content}}</pre>
		</div>
		
		<div>
			<h3>This page can be found @ /pages/about/index.vue</h3>
		</div>
		
		</div>
</template>

<script>
// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	// layout: 'home',
	async fetch() {
		this.about = await fetch('http://cm.beneb.com/wp-json/wp/v2/pages/8').then((res) =>
			res.json(),
		)
	},
	data() {
		return {
			about: [],
			
		}
	},
}
</script>

<style scoped>
    @import url('~assets/css/style.css');
</style>