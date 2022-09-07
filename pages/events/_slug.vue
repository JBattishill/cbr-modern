<template>
    <article>
      <h1>{{ event.title }}</h1>
      <p v-if="$fetchState.pending">
        <span class="loading"></span>
      </p>
      <p v-else-if="$fetchState.error">Error while fetching events 🤬</p>
      <section>
        <img :src="event.image" :alt="event.title" />
        <p>{{ event.content }}</p>
      </section>
      <button @click="goBack">Back</button>
    </article>
  </template>

  <script>



  export default {
    data() {
      return {
        event: {}
      }
    },
    async fetch() {
      this.event = await this.$http.$get(
        `http://cm.beneb.com/wp-json/wp/v2/events/?per_page=100/${this.$route.params.slug}`
      )
    },
    methods: {
      goBack() {
        return this.$router.go(-1)
      }
    }
  }
  
  </script>
  <style scoped>
  article {
    max-width: 600px;
    margin: 0 auto;
  }
  img {
    height: 200px;
  }
  p {
    text-align: left;
  }
  </style>
  