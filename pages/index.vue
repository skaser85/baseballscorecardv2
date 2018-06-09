<template>
  <div id="app">
    <!-- <AddPlayersList side="Home" team="Cincinnati Reds" class="slot" /> -->
    <AddPlayerForm side="Home" team="Cincinnati Reds" class="slot" />
    <!-- <StartScreen v-if="!side" @team-select="teamSelect" :teams="teamsPlaying" class="slot" />
    <SelectTeam v-if="side" @team-selected="teamSelected" :side="side" :teams="teams" class="slot" /> -->
    <FooterBase />
  </div>
</template>

<script>
import FooterBase from "../components/FooterBase.vue";
import StartScreen from "../components/StartScreen.vue";
import SelectTeam from "../components/SelectTeam.vue";
import AddPlayersList from "../components/AddPlayersList.vue";
import AddPlayerForm from "../components/AddPlayerForm.vue";

export default {
  name: "app",
  components: {
    FooterBase,
    StartScreen,
    SelectTeam,
    AddPlayersList,
    AddPlayerForm
  },
  methods: {
    teamSelect(side) {
      this.side = side.toLowerCase();
    },
    teamSelected(team) {
      this.teamsPlaying[this.side] = team;
      this.side = null;
    }
  },
  data() {
    return {
      side: null,
      teamsPlaying: {
        home: null,
        away: null
      },
      teams: [
        {
          teamName: "Chicago Cubs",
          city: "Chicago",
          name: "Cubs",
          // logoUrl: "@assets/CHC-2018.png"
          logoUrl: "CHC-2018"
        },
        {
          teamName: "Cincinnati Reds",
          city: "Cincinnati",
          name: "Reds",
          logoUrl: "./assets/logos/CIN-2018.png"
        },
        {
          teamName: "Cleveland Indians",
          city: "Cleveland",
          name: "Indians",
          logoUrl: "./assets/logos/CLE-2018.png"
        },
        {
          teamName: "Colorado Rockies",
          city: "Colorado",
          name: "Rockies",
          logoUrl: "./assets/logos/COL-2018.png"
        },
        {
          teamName: "Detroit Tigers",
          city: "Detroit",
          name: "Tigers",
          logoUrl: "./assets/logos/DET-2018.png"
        },
        {
          teamName: "Milwaukee Brewers",
          city: "Milwaukee",
          name: "Brewers",
          logoUrl: "./assets/logos/MIL-2018.png"
        },
        {
          teamName: "Pittsburgh Pirates",
          city: "Pittsburgh",
          name: "Pirates",
          logoUrl: "./assets/logos/PIT-2018.png"
        },
        {
          teamName: "St. Louis Cardinals",
          city: "St. Louis",
          name: "Cardinals",
          logoUrl: "./assets/logos/STL-2018.png"
        }
      ]
    };
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.slot {
  flex: 1;
}
</style>