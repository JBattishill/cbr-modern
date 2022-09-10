<template>
	<div class="wrapper">
		{{about}}
	</div>
</template>

<script>
	export default {
		data() {
		return {
     //empty array to be filled with all events
			about: [],
		//tags in a string to capture to beignning and end point of <h4> tags - used to target heading 
			body: "<h4>",
			bodyEnd: "</h4>",
			str: "",
		}
	},

//now go get the data
async fetch() {
		//make the api call and fill the empty events array
		let apiData = await fetch('http://cm.beneb.com/wp-json/wp/v2/pages/157')
		.then((response) =>
			response.json()
		)
		// Below code not used at this stage, can be used with data varaibles for H4 tags above to target code between 2 html tags
		// let strippedString = originalString.substring(originalString.indexOf(this.body)+this.body.length,originalString.indexOf(this.bodyEnd))
			
		//stripping page data of html tags
		let strippedString = apiData.content.rendered.replace(/(<([^>]+)>)/gi, "");
		let apostropheString = strippedString.replace('&#8217;', "'");
		let spaceString = apostropheString.replace('&nbsp;', " ")
		let deadSpaceString = spaceString.replace('&#8211;',"")
		
		let cleanString = deadSpaceString;

		//setting the variable 'about' to hold the string that is now stripped of html tags
                this.about = cleanString;
	},
}
</script>

<!-- Connecting to CSS stylesheet -->
<style scoped>
    @import url('~assets/css/style.css');
</style>