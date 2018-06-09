<template>
  <div class="teams">
    <StartTeam v-if="!teams.away" @team-select="teamSelect" class="team" side="Away" b-color="#8A8D8F" />
    <StartAddPlayers v-else class="team" side="Away" b-color="#8A8D8F" t-color="#F2F2F2" :team-name="teams.away" />
    <StartTeam v-if="!teams.home" @team-select="teamSelect" class="team" side="Home" b-color="#E0E0E0" />
    <StartAddPlayers v-else class="team" side="Home" b-color="#E0E0E0" t-color="#333333" :team-name="teams.home" />
  </div>
</template>

<script>
import StartTeam from "./StartTeam.vue";
import StartAddPlayers from "./StartAddPlayers.vue";

export default {
  props: ["teams"],
  components: {
    StartTeam,
    StartAddPlayers
  },
  methods: {
    teamSelect(side) {
      this.$emit("team-select", side);
    }
  }
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
