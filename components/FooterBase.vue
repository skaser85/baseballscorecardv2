<template>
  <div>
    <footer>
      <span>Baseball Scorecard</span>
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/></svg>
    </footer>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
footer {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 1em;
  height: 50px;
  font-family: "Lobster", cursive;
  color: white;
  background: #27ae60;
}

span {
  font-size: 24px;
}

svg {
  fill: white;
  width: 30px;
  height: 30px;
}
</style>
