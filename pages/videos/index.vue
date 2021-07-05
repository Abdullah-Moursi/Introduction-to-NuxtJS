<template>
  <div class="app">
    <nuxt-child />
    <h1>videos</h1>
    <div v-for="video in videos" :key="video.id">
      <nuxt-link :to="`/videos/${video.id}`">
        {{ video.name }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  async fetch({$axios, store}) {
    let response = await $axios.get('/videos')
    let videos = response.data.data.map(v => v.attributes)

    store.commit('SET_VIDEOS', videos)
  },
}
</script>

<style></style>
// computed: { // video () { // return this.videos.find( // v => v.id ===
this.$route.params.id // ) // }
