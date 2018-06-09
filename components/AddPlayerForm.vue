<template>
  <div class="add-player-form-container">
      <span class="title">{{ side }} - {{ team }} - Add Player</span>
      <div class="add-player-form">
        <div class="row">
          <label for="batting-order">Batting Order:</label>
          <select id="batting-order" class="input" ref="battingOrder">
            <option>Select Batting Order</option>
            <option v-for="n in 9" :key="n" :value="n">{{ n }}</option>
          </select>
        </div>
        <div class="row">
          <label for="number">Number:</label>
          <input id="number" class="input" type="number" placeholder="Player's jersey number" ref="number" />
        </div>
        <div class="row">
          <label for="position">Position:</label>
          <select id="position" class="input" ref="position">
            <option>Select Fielding Postion</option>
            <option v-for="pos in positions" :key="pos" :value="pos">{{ pos }}</option>
          </select>
        </div>
        <div class="row">
          <label for="name">Player Name:</label>
          <input id="name" class="input" type="text" placeholder="Player's name" ref="name" />
        </div>
        <div class="row add-player-btn">
          <div class="btn" @click="addPlayer"><span class="inner">Add Player</span> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M9.3 8.7a1 1 0 0 1 1.4-1.4l4 4a1 1 0 0 1 0 1.4l-4 4a1 1 0 0 1-1.4-1.4l3.29-3.3-3.3-3.3z"/></svg></div>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  props: ["side", "team"],
  data() {
    return {
      positions: ["SP", "C", "1B", "2B", "3B", "SS", "RF", "CF", "LF", "DH"]
    };
  },
  methods: {
    addPlayer() {
      let bo = this.$refs.battingOrder;
      let no = this.$refs.number;
      let pos = this.$refs.pos;
      let name = this.$refs.name;
    }
  }
};
</script>

<style>
.add-player-form-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.title {
  align-self: flex-start;
  padding-bottom: 50px;
  font-family: "Lobster", cursive;
  font-size: 18px;
}

.add-player-form {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.row {
  width: 95%;
  height: 30px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 40px;
  font-family: "Prompt", sans-serif;
  font-size: 18px;
}

.input {
  width: 200px;
  height: 100%;
  text-align: center;
}

.btn {
  width: 150px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  background: #c4c4c4;
  box-shadow: 4px 4px 4px #666;
}

.add-player-btn {
  justify-content: flex-end;
}
</style>
