<template>
	<div>
	  <p v-if="$fetchState.pending">
		<span class="loading"></span>
	  </p>
	  <p v-else-if="$fetchState.error">Error while fetching events, please try again</p>
	  <ul class="eventsWrapper" v-else>
		<li class="events" v-for="event in events" :key="event.id">
		  <NuxtLink
			:to="{ name: 'events-slug', params: { slug: event.slug } }"
		  >
			{{ event.title.rendered }}
			: {{ event.acf.year }}
		  </NuxtLink>
		</li>
	  </ul>
	  <button @click="$fetch">Refresh Data</button>
	</div>
  </template>

  <script>
  export default {
	data() {
	  return {
		events: [],
		year: ['2017']
	  }
	},
	activated() {
	  if (this.$fetchState.timestamp <= Date.now() - 30000) {
		this.$fetch()
	  }
	},
  
	async fetch() {
	//   this.events = await this.$http.$get('http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100')
	// },

	const events = await fetch(
    `http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100/${this.$route.params.acf.year}`
  ).then((res) => res.json())
  
  if (events.id && article.user.username === this.$route.params.username) {
    this.events = events
    this.$store.commit('2017', this.events)


//    computed: {
//     // a computed getter
// 		eventCount2017() {
// 		// `this` points to the component instance
// 		return count.this.events.acf.year
// 		}
// 	}
}}}
  </script>
  <style scoped>
  li {
	margin-bottom: 0.5rem;
  }
  li:first-letter {
	text-transform: uppercase;
  }
  .loading {
	display: inline-block;
	width: 1.5rem;
	height: 1.5rem;
	border: 4px solid rgba(9, 133, 81, 0.705);
	border-radius: 50%;
	border-top-color: #158876;
	animation: spin 1s ease-in-out infinite;
  }
  @keyframes spin {
	to {
	  -webkit-transform: rotate(360deg);
	}
  }
  </style>