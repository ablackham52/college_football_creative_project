<template>
<div class="wrapper">
  <div class="teams">
    <div class="team" v-for="team in teams" :key="team.id">
      <div class="image">
        <img :src="'/images/teams/'+team.image">
      </div>
      <div class="info">
        <h1>#{{team.ranking}}</h1>
        <h1>{{team.name}}</h1>
      </div>

      <div class="buttons">
      <router-link to="/team">
        <button @click="set_team(team)">Team Info</button>
      </router-link>
      <div  @click="toggle(team)" class="auto">
          <img v-if="team_is_favorite(team)" src="/images/blackStar.png">
          <img v-else="" src="/images/whiteStar.png">
      </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TeamList',
  props: {
    teams: Array
  },
  methods: {
    toggle(team){
      if(this.$root.$data.favorites.includes(team)){
        var index = this.$root.$data.favorites.indexOf(team)
        this.$root.$data.favorites.splice(index, 1)
      }
      else{
      this.$root.$data.favorites.push(team);
      }
    },
    team_is_favorite(team){
      return this.$root.$data.favorites.includes(team)
    },
    set_team(team){
      this.$root.$data.team = team;
    }

  }
}

</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.teams {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.team {
  margin: 33px;
  margin-top: 50px;
  width: 200px;
}

.team img {
  height: 250px;
  width: 200px;
  object-fit: contain;
}

.team .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: white;
  color: #000;
  display: flex;
  justify-content: center;
  height: 70px;
}

.info h1 {
  margin-top: auto;
  margin-bottom: auto;
  margin-left: 7px;
  margin-right: 7px;
  font-size: 24px;
}

.buttons {
  display: flex;
  justify-content: space-around;
}

button {
  height: 50px;
  padding: 10px 10px;
  background: #000;
  color: white;
  border: none;
}

.auto img {
  width: 50px;
  height: 50px;
}
</style>
