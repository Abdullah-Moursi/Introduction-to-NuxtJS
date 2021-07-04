<template>
  <div class="app">
    <nuxt-child />
    <h1>videos</h1>
    <ul v-for="video in videos" :key="video.id">
      <nuxt-link :to="`/videos/${video.id}`">
      {{
        video.name
      }}
      </nuxt-link>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      videos: [
        {
          id: '16',
          name: 'V'
        },
        {
          id: '1',
          name: 'X'
        },
        {
          id: '71',
          name: 'Z'
        }
      ]
    }
  },
  computed: {
    video () {
      return this.videos.find(
        v => v.id === this.$route.params.id
      )
    }
  }
}
</script>

<style></style>
