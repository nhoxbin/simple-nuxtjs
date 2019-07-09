<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        simple-nuxtjs
      </h1>
      <h2 class="subtitle">
        My awe-inspiring Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link
          v-for="(post, index) in posts"
          :key="index"
          :to="{name: 'post-id', params: {id: post.id}}"
          class="button--grey">
          {{ post.title }}
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  },
  head() {
    return {
      title: 'Home page',
      meta: [
        { name: 'twitter:title', content: 'Nuxt Fundamentals by Vue School' },
        { name: 'twitter:description', content: 'Nuxt + Vue School = Great' },
        { name: 'twitter:image', content: 'https://i.imgur.com/UYP2umJ.png' },
        { name: 'twitter:card', content: 'summary_large_image' }
      ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all;
    }
  }
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
