<template>
  <a :class="['player-card', player.position]" :href="profilePageUrl" target="_blank" rel="norefferer">
    <h3>{{`${player.firstName} ${player.surname}`}}</h3>
    <div class="info">
      <div class="country">{{player.country}}</div>
      <div class="number">{{player.shirtNumber === "unknown" ? "TBC" : player.shirtNumber}}</div>
      <div class="position">{{player.position}}</div>
    </div>
    <div class="img">
      <img :src="player.squadImage" :alt="`Profile picture of ${player.firstName} ${player.surname}`">
    </div>
    <div class="join-date">
      {{`Signed : ${player.joinDate}`}}
    </div>
  </a>
</template>

<script>
export default {
  name: 'PlayerCard',
  props: {
    player: {
      country: String,
      firstName: String,
      surname: String,
      squadImage: String,
      joinDate: String,
      position: String,
      shirtNumber: String,
      profilePageUrl: String
    }
  }
}
</script>

<style scoped>
  .player-card {

  }
</style>
