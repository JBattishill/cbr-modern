
<template>
	<div class="container">
		<SiteNavigation />
		<h2>{{ $route.params.slug }}</h2>
		<div class="about">
			<!-- the data returns an array with one item in it, so need to reference it below -->
			<h2>{{  page[0].title.rendered  }}</h2>

			<!-- create a div to hold the renderedContent variable holding the data we've retrieved below -->
			<!-- if we don't use the v-html tag it will render it as a string -->
			<div class="" v-html="renderedContent"></div>

			<!-- <pre>{{ $data }}</pre> -->
		</div>
	</div>
</template>

<script>
// in this API call, we load a page based off the URL paramter
// we access what is in the URL by using the params object
export default {
	async asyncData({ params }) {
		//page returns the data so we can access it below
		const page = await fetch(
			`http://cm.beneb.com/wp-json/wp/v2/pages/?slug=links`
		).then((res) => {
			if (res.ok) {
				return res.json()
			}
			throw new Error(res.status)
		})
		//now we've got the data, lets create a new variable to hold just the rendered content
		let renderedContent = page[0].content.rendered;
		//return the renderedContent
		return {renderedContent, page}
		
		//return all page data
		
	},
}
</script>