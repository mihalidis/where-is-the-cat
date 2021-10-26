<template>
<!--  Dynamic Components  -->
  <transition-group name="slideContainer" mode="out-in">
    <component @activeComponent="activeComponent = $event" key="mainComponent" :is="activeComponent"></component>
    <canvas key="canvas" id="canvas" v-show="activeComponent === 'celebrate'"></canvas>
  </transition-group>
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

.slideContainer-enter{}
.slideContainer-enter-active{
  animation: slide-in .3s ease-out forwards;
}
.slideContainer-leave{}
.slideContainer-leave-active{
  animation: slide-out .3s ease-out forwards;
}

@keyframes slide-in {
  from{
    transform: translateX(-1000px);
    opacity: 0;
  }
  to{
    transform: translateX(0px);
    opacity: 1;
  }
}
@keyframes slide-out {
  from{
    transform: translateX(0px);
    opacity: 1;
  }
  to{
    transform: translateX(1000px);
    opacity: 0;
  }
}
</style>
