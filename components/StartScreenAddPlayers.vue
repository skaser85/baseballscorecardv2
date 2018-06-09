<template>
  <div class="teams">
    <StartAddPlayers class="team" side="Away" b-color="#8A8D8F" :team="homeTeam"/>
    <StartAddPlayers class="team" side="Home" b-color="#E0E0E0" :team="awayTeam"/>
  </div>
</template>

<script>
import StartAddPlayers from "./StartAddPlayers.vue";

export default {
  props: ["homeTeam", "awayTeam"],
  components: {
    StartAddPlayers
  },
  methods: {}
};
</script>

<style scoped>
.teams {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.team {
  flex: 1;
}
</style>
