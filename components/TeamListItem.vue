<template>
  <div class="team-container" @click="teamSelected">
    <!-- <img src="~assets/logos/CHC-2018.png" :alt="name" /> -->
    <!-- <div class="image" :style="{ backgroundImage: 'url(' + source + ')' }"></div> -->
    <span class="team-pic">{{ source }}</span>
    <div class="right">
      <span class="team-name">{{ name }}</span>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M5 3h14a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5c0-1.1.9-2 2-2zm0 2v14h14V5H5zm8 6h2a1 1 0 0 1 0 2h-2v2a1 1 0 0 1-2 0v-2H9a1 1 0 0 1 0-2h2V9a1 1 0 0 1 2 0v2z"/></svg>
    </div>
  </div>
</template>

<script>
export default {
  props: ["logo", "name"],
  computed: {
    source() {
      return this.name.split("")[0].toUpperCase();
    }
  },
  methods: {
    teamSelected() {
      this.$emit("team-selected", this.name);
    }
  }
};
</script>

<style scoped>
.team-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  width: 315px;
  background: white;
  border-radius: 10px;
  padding: 0 10px;
  height: 50px;
}

.team-pic {
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: "Pronto", sans-serif;
  font-size: 36px;
  font-weight: 500;
}

.team-name {
  font-family: "Lobster", cursive;
  font-size: 18px;
  padding-left: 20px;
}

.right {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
