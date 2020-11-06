<template>
<div>
  <TeamList :teams="teams" />
</div>
</template>

<script>
import TeamList from "../components/TeamList.vue"
export default {
  name: 'Home',
  components: {
    TeamList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    teams() {
      return this.$root.$data.teams;
    }
  },
}
</script>
