<template>
  <div class="image-wrapper">
    <img src="../src/assets/question.png" alt="question">
  </div>
</template>

<script>
export default {
  name: "DefaultCard",
}
</script>

<style scoped>
.image-wrapper {
  max-width: 210px;
  max-height: 210px;
  border-radius: 8px;
  border: 1px solid #664E88;
  cursor: pointer;
  margin-top: 32px;
  box-shadow: 0px 9px 55px #666;
}

.image-wrapper:hover {
  box-shadow: 0px 0px 13px 0px rgba(102,78,136,1);
  transition: box-shadow .5s;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  border-radius: 8px;
}
</style>