<template>
  <section class="player-listing">
    <h1 class="heading">Players</h1>
    <section class="player-container">
      <player-card v-for="player in players" :player="player" :key="player.squadImage"/>
    </section>
  </section>
</template>

<script>
import playerData from '../data/players';
import PlayerCard from './PlayerCard.vue'
export default {
  name: 'PlayerListing',
  components: {
    PlayerCard
  },
  data: function (){
    return {
      players: playerData.players
    }
  }
}
</script>

<style scoped>
  .player-listing{
    min-height: 100vh;
    width: 90%;
    max-width: 1500px;
    background-color: white;
    margin: 0 auto;
    padding: 1rem 0.5rem;
  }
  .heading{
    margin: 0;
  }

  .player-container {
    display: grid;
    grid-template-columns: 30% 30% 30%;
    gap: 5%;
  }

  @media (max-width: 800px){
    .player-container{
      display: flex;
      flex-direction: column;
    }
  }
</style>
