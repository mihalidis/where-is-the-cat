<template>
<!--  Dynamic Components  -->
  <component :is="activeComponent"></component>
</template>
<script>
import gameCards from "../components/GameCards";
import failure from "../components/Failure";
import celebrate from "../components/Celebrate";

export default {
  components: {
    gameCards,
    failure,
    celebrate
  },
  data() {
    return {
      activeComponent : "gameCards",
    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@100;500&display=swap');
*, *::before, *::after {
  box-sizing: border-box;
}
body {
  height: 100vh;
  background: rgb(2,0,36);
  background: linear-gradient(185deg, rgba(2,0,36,1) 0%, rgba(255,255,255,1) 0%, rgba(169,228,215,0.5326505602240896) 100%);
}
body, html {
  overflow: hidden;
}
</style>
