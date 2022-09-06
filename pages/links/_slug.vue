<template>
	<div class="container">
		<h2>{{  $route.params.slug  }}</h2>
		<h3>Filename: pages/events/_slug.vue</h3>

		<SiteNavigation />

		<div class="events">
			<!-- the buiding returns an array with one item in it, so need to reference it below -->
			<h2>{{  events[0].title.rendered  }}</h2>

			<ul>
				<li>Address: {{  events[0].acf.location  }}</li>
				<li>Suburb: {{  events[0].acf.suburb  }}</li>
				<li>Architect: {{  events[0].acf.architect[0].name  }}</li>
			</ul>
			<!-- <pre>{{ $data }}</pre> -->
		</div>
	</div>
</template>

<script>
// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	async asyncData({ params }) {
		const events = await fetch(
			// `http://cm.beneb.com/wp-json/wp/v2/buildings/143`
			// `https://cm.beneb.com/wp-json/wp/v2/buildings/?slug=high-court-of-australia`
			`http://cm.beneb.com/wp-json/wp/v2/events/?slug=${params.slug}`
		).then((res) => {
			if (res.ok) {
				return res.json()
			}
			throw new Error(res.status)
		})
		return { events }
	},
}
</script>
