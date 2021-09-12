<template>
  <a :class="['player-card', player.position]" :href="player.profilePageUrl" target="_blank" rel="norefferer">
    <h3 class="name">{{`${player.firstName} ${player.surname}`}}</h3>
    <div class="main-card-section">
      <div class="info">
      <p class="country">{{player.country}}</p>
      <p class="number">{{player.shirtNumber === "unknown" ? "NA" : player.shirtNumber}}</p>
      <p class="position">{{player.position}}</p>
    </div>
    <div class="img">
      <img :src="player.squadImage" :alt="`Profile picture of ${player.firstName} ${player.surname}`">
    </div>
    </div>
    <div class="join-date">
      {{`Signed : ${player.joinDate || 'TBC'}`}}
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
    display: flex;
    flex-direction: column;
    padding: 1rem;
    box-shadow: 0 0 5px rgb(126, 126, 126);
  }
  .player-card:hover{
    box-shadow: 0 0 5px rgb(29, 29, 29);
  }

  @media (max-width: 1000px){
    .player-card{
      width: 400px;
      max-width: 90%;
      margin: 0 auto;
    }
  }
  .main-card-section {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
  }
  .img img {
    width: 200px;
    height: auto;
  }
  .number {
    font-size: 3rem;
    margin: 0 0.5rem;
    color: white;
    text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
    1px 1px 0 #000;
  }

  .name {
    margin: 0;
  }

  .join-date, .name {
    text-align: center;
  }

  .Goalkeeper {
    background-color: #d63031;
  }

  .Defender {
    background-color: #fdcb6e;
  }

  .Midfielder {
    background-color: #55efc4;
  }

  .Forward {
    background-color: #0984e3;
  }
  
</style>
