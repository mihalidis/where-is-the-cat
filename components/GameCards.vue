<template>
<div class="game-cards">
  <h1>Where is the cat?</h1>
  <p>After choosing one of the open cards, click the closed card.</p>
  <div class="cards-wrapper">
    <div class="card" v-for="(image, index) in imgResource" :key="index">
      <card :img-source="image.source" :img-alt-text="image.name" />
    </div>
  </div>
</div>
</template>

<script>
import card from "./Card";
export default {
  name: "GameCards",
  components: {
    card,
  },
  data() {
    return {
      imgResource: [
        {
          id:'1',
          name:'card-1',
          source:'/src/assets/card-1.jpg'
        },
        {
          id:'2',
          name:'card-2',
          source:'/src/assets/card-2.jpg'
        },
        {
          id:'3',
          name:'card-3',
          source:'/src/assets/card-3.jpg'
        },
        {
          id:'4',
          name:'card-4',
          source:'/src/assets/card-4.jpg'
        },
        {
          id:'5',
          name:'card-5',
          source:'/src/assets/card-5.jpg'
        },
      ]
    }
  }
}
</script>

<style scoped>
.game-cards {
  margin: 120px auto 64px;
  max-width: 90%;
  text-align: center;
  font-family: 'Montserrat', sans-serif;
}
.game-cards h1 {
  color: #4B3869;
}
.game-cards p {
  color: #664E88;
}

.cards-wrapper {
  display: flex;
  justify-content: space-between;
}
</style>