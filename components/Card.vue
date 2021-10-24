<template>
<div class="image-wrapper" @click="$emit('selected')">
  <img :src="`..${imgSource}`" :alt="imgAltText">
</div>
</template>

<script>
export default {
  name: "Card",
  props: {
    imgSource: String,
    imgAltText: String,
  }
}
</script>

<style scoped>
.image-wrapper {
  max-width: 210px;
  max-height: 210px;
  border-radius: 8px;
  border: 1px solid #664E88;
  cursor: pointer;
  transition: box-shadow .5s;
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