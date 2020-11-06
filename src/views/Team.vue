<template>
<div>
  <TeamInfo :team="this.$root.$data.team" />
</div>
</template>

<script>
import TeamInfo from "../components/TeamInfo.vue"
export default {
  name: 'Team',
  components: {
    TeamInfo
  },
}
</script>
