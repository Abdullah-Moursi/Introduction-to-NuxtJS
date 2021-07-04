<template>
<div>
    <nuxt-child :video="video" />
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