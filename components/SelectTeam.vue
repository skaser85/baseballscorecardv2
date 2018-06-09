<template>
  <div class="container" @team-selected="teamSelected">
    <span class="team-select-title">Select {{ side }} Team</span>
    <div class="team-list">
      <TeamListItem class="team-list-item" v-for="team in teams" :key="team.name" 
                    :logo="team.logoUrl" :name="team.teamName" @team-selected="teamSelected"/>
    </div>
  </div>
</template>

<script>
import TeamListItem from "./TeamListItem.vue";
export default {
  props: ["side", "teams"],
  components: {
    TeamListItem
  },
  data() {
    return {
      team: null
    };
  },
  methods: {
    teamSelected(team) {
      this.$emit("team-selected", team);
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

.team-select-title {
  font-family: "Lobster", cursive;
  font-size: 24px;
  /* align-self: flex-start; */
  margin: 0.5em 0;
}

.team-list {
  width: 335px;
  height: 76vh;
  background: #eee;
  padding: 5px 0;
  box-shadow: 2px 2px 6px #666;
  overflow-y: scroll;
  overflow-x: hidden;
}

.team-list-item {
  margin: 5px;
}
</style>
