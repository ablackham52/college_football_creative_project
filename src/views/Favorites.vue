<template>
<div>
  <h1 v-if="this.$root.$data.favorites.length===0">You Have No Favorites</h1>
  <TeamList :teams="this.$root.$data.favorites" />
</div>
</template>

<script>
import TeamList from "../components/TeamList.vue"
export default {
  name: 'Favorites',
  components: {
    TeamList
  },
}
</script>

<style scoped>
div {
  text-align: center;
}
</style>
