<template>
  <section>
    <background />
    <player-listing />
  </section>
</template>

<script>
import Background from './Background.vue';
import PlayerListing from '../PlayerListing.vue';
export default {
  components: {
    Background,
    PlayerListing
  },
  name: 'Layout'
}
</script>

<style scoped>
</style>
