<template>
  <div class="container">
    <img src="../src/assets/table-cat.jpg" alt="table cat">
    <h2>Game Over</h2>
    <button class="play-again-btn" @click="playAgain">Play Again!</button>
  </div>
</template>

<script>
export default {
  name: "Failure",
  methods: {
    playAgain() {
      location.reload();
    }
  }
}
</script>

<style scoped>
.container {
  margin: 120px auto 64px;
  max-width: 1163px;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
}

.play-again-btn {
  padding: 12px;
  background-color: #3D2C8D;
  color: #fff;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}
</style>