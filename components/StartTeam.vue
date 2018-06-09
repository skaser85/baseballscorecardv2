<template>
  <div class="container" :style="{background: bColor}">
    <div class="select-team" @click="selectTeam">
      <span>Select {{ side }} Team</span>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M12 22a10 10 0 1 1 0-20 10 10 0 0 1 0 20zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm1-9h2a1 1 0 0 1 0 2h-2v2a1 1 0 0 1-2 0v-2H9a1 1 0 0 1 0-2h2V9a1 1 0 0 1 2 0v2z"/></svg>
    </div>
  </div>
</template>

<script>
export default {
  props: ["side", "bColor"],
  methods: {
    selectTeam() {
      this.$emit("team-select", this.side);
    }
  }
};
</script>

<style scoped>
.container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.select-team {
  background: #c4c4c4;
  width: 225px;
  height: 200px;
  border-radius: 25px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 0 5px;
}

span {
  text-align: center;
  font-family: "Prompt", sans-serif;
  font-size: 36px;
  font-weight: 500;
  font-style: italic;
}

svg {
  width: 60px;
  height: 60px;
}
</style>
