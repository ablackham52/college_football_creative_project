<template>
<div class="wrapper">
  <div class="team">
    <div class="brand">
      <img :src="'/images/teams/'+team.image">
      <div class="record">
        <h1>#{{team.ranking}} {{team.name}}</h1>
        <h2>{{team.record}}</h2>
      </div>
    </div>
    <div class="main">
      <div class="info">
        <p>Head Coach: {{team.coach}}</p>
        <p>Quarterback: {{team.quarterback}}</p>
      </div>
      <div @click="toggle(team)" class="auto">
        <img v-if="team_is_favorite(team)" src="/images/blackStar.png">
        <img v-else="" src="/images/whiteStar.png">
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TeamInfo',
  props: {
    team: Object
  },
  methods: {
    toggle(team) {
      if (this.$root.$data.favorites.includes(team)) {
        var index = this.$root.$data.favorites.indexOf(team)
        this.$root.$data.favorites.splice(index, 1)
      } else {
        this.$root.$data.favorites.push(team);
      }
    },
    team_is_favorite(team) {
      return this.$root.$data.favorites.includes(team)
    }

  }
}
</script>


<style scoped>
.brand {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.record {
  margin-left: 70px;
  text-align: center;
}

h1 {
  font-size: 54px;
  margin-bottom: 15px;
}

h2 {
  margin-top: 0px;
  font-size: 60px;
}

.main {
  text-align: center;
  font-size: 32px;
}

.auto img {
  width: 50px;
  height: 50px;
}
</style>
