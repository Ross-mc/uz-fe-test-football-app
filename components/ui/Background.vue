<template>
  <img :src="backgroundImg" alt="Premier League background Pattern" class="background-image">
</template>

<script>
import backgroundImg from '../../assets/images/background-image.jpg';
export default {
  name: 'Background',
  data: function() {
    return {
      backgroundImg
    }
  }
}
</script>

<style scoped>
  .background-image{
    width: 100%;
    height: 100%;
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    z-index: -10;
    display: block;
    object-fit: cover;
  }
</style>
