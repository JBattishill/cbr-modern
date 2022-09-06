<template>
	<div class="container">
		<h2>All events</h2>
		<h3>Filename: pages/events/2022/index.vue</h3>

		<SiteNavigation />


		<div class="events">
			<h1>This is the 2022 events page</h1>
			<EventsNav />

			<!-- The building list is over in the components folder -->
			<!-- the code below loads the component here so we can use it again -->
			<EventsList />

			<!-- this is a really useful line of code that will just output what the API call returns -->
			<!-- <pre>{{ $data }}</pre> -->
		</div>
	</div>
</template>

<script>
// const years: ['2016', '2017', '2018', '2019', '2020', '2021', '2022', '2023', '2024', '2025', '2026', '2027', '2028', '2029', '2030', '2031', '2032']);


// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	async asyncData({ params }) {
		const events = await fetch(
			`http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100`
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