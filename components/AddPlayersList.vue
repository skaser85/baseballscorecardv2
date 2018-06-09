<template>
  <div class="add-players-container">
    <div class="top">
      <span class="title">{{ side }} - {{ team }} - Add Players</span>
      <div class="add-new-player-btn"><span>Add New Player</span> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M5 3h14a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5c0-1.1.9-2 2-2zm0 2v14h14V5H5zm8 6h2a1 1 0 0 1 0 2h-2v2a1 1 0 0 1-2 0v-2H9a1 1 0 0 1 0-2h2V9a1 1 0 0 1 2 0v2z"/></svg></div>
    </div>
    <div class="bottom">
      <div class="header box">
        <span class="box-item header-info right-border">Batting<br>Order</span>
        <span class="box-item header-info right-border">Number</span>
        <span class="box-item header-info right-border">Position</span>
        <span class="box-item header-info name">Player Name</span>
      </div>
      <div class="box" v-for="player in players" :key="player.bo">
        <span class="box-item player-info right-border">{{ player.bo }}</span>
        <span class="box-item player-info right-border">{{ player.no }}</span>
        <span class="box-item player-info right-border">{{ player.pos }}</span>
        <div class="box-item player-name name"><span>{{ player.name }}</span> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M9 4.58V4c0-1.1.9-2 2-2h2a2 2 0 0 1 2 2v.58a8 8 0 0 1 1.92 1.11l.5-.29a2 2 0 0 1 2.74.73l1 1.74a2 2 0 0 1-.73 2.73l-.5.29a8.06 8.06 0 0 1 0 2.22l.5.3a2 2 0 0 1 .73 2.72l-1 1.74a2 2 0 0 1-2.73.73l-.5-.3A8 8 0 0 1 15 19.43V20a2 2 0 0 1-2 2h-2a2 2 0 0 1-2-2v-.58a8 8 0 0 1-1.92-1.11l-.5.29a2 2 0 0 1-2.74-.73l-1-1.74a2 2 0 0 1 .73-2.73l.5-.29a8.06 8.06 0 0 1 0-2.22l-.5-.3a2 2 0 0 1-.73-2.72l1-1.74a2 2 0 0 1 2.73-.73l.5.3A8 8 0 0 1 9 4.57zM7.88 7.64l-.54.51-1.77-1.02-1 1.74 1.76 1.01-.17.73a6.02 6.02 0 0 0 0 2.78l.17.73-1.76 1.01 1 1.74 1.77-1.02.54.51a6 6 0 0 0 2.4 1.4l.72.2V20h2v-2.04l.71-.2a6 6 0 0 0 2.41-1.4l.54-.51 1.77 1.02 1-1.74-1.76-1.01.17-.73a6.02 6.02 0 0 0 0-2.78l-.17-.73 1.76-1.01-1-1.74-1.77 1.02-.54-.51a6 6 0 0 0-2.4-1.4l-.72-.2V4h-2v2.04l-.71.2a6 6 0 0 0-2.41 1.4zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm0-2a2 2 0 1 0 0-4 2 2 0 0 0 0 4z"/></svg></div>        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["side", "team"],
  data() {
    return {
      players: [
        {
          bo: 1,
          no: 33,
          pos: "LF",
          name: "Jesse Winker"
        },
        {
          bo: 2,
          no: 3,
          pos: "C",
          name: "Tucker Barnhart"
        },
        {
          bo: 3,
          no: 19,
          pos: "1B",
          name: "Joey Votto"
        },
        {
          bo: 4,
          no: 14,
          pos: "RF",
          name: "Scott Schebler"
        },
        {
          bo: 5,
          no: 4,
          pos: "2B",
          name: "Scooter Gennett"
        }
      ]
    };
  }
};
</script>

<style scoped>
.add-players-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.top {
  width: 90%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-bottom: 10px;
  border-bottom: 1px solid #aaa;
}

.title {
  align-self: flex-start;
  padding-bottom: 10px;
  font-family: "Lobster", cursive;
  font-size: 18px;
}

.add-new-player-btn {
  align-self: flex-end;
  padding-top: 10px;
  font-family: "Prompt", sans-serif;
  font-size: 14px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  height: 50px;
}

.add-new-player-btn span {
  padding-right: 8px;
}

.bottom {
  width: 90%;
  height: 70vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.box {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  height: 60px;
  border-bottom: 1px solid #aaa;
}

.box-item {
  height: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.header-info {
  font-family: "Prompt", sans-serif;
  font-size: 10px;
  text-align: left;
}

.right-border {
  width: 50px;
  border-right: 1px solid #aaa;
}

.name {
  width: 180px;
}

.player-info {
  font-family: "Lobster", cursive;
  font-size: 18px;
}

.player-name {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding-left: 10px;
  font-family: "Prompt", sans-serif;
  font-size: 14px;
}
</style>
