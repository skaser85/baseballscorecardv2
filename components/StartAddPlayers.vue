<template>
  <div class="container" :style="{background: bColor}">
    <span class="side-title" :style="{color: tColor}">{{ side }} Team</span>
    <div class="middle">
      <span class="team-name">{{ teamName }}</span>
      <div class="btn" @click="addPlayers"><span class="inner">Add Players</span> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M9.3 8.7a1 1 0 0 1 1.4-1.4l4 4a1 1 0 0 1 0 1.4l-4 4a1 1 0 0 1-1.4-1.4l3.29-3.3-3.3-3.3z"/></svg></div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["side", "bColor", "tColor", "teamName"],
  methods: {
    addPlayers() {
      this.$emit("add-players", { side: this.side, team: this.teamName });
    }
  }
};
</script>

<style scoped>
.container {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
}

.side-title {
  font-family: "Lobster", cursive;
  font-size: 18px;
  position: absolute;
  top: 10px;
  left: 15px;
}

.team-name {
  font-family: "Lobster", cursive;
  font-size: 36px;
}

.middle {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 20vh;
}

.btn {
  width: 175px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  background: #c4c4c4;
  box-shadow: 4px 4px 4px #666;
}

.inner {
  font-family: "Prompt", sans-serif;
  font-size: 20px;
}

svg {
  width: 40px;
  height: 45px;
}
</style>
