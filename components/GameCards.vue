<template>
<div class="game-cards">
  <h1>Where is the cat?</h1>
  <p>After choosing one of the open cards, click the closed card.</p>
  <div class="cards-wrapper">
    <div
        v-for="(image, index) in imgResource"
        :key="index"
        class="card"
        :class="{'selected-card' : image.name === cardSelect}"
    >
      <card :img-source="image.source" :img-alt-text="image.name" @selected="selectedCard(image)"/>
    </div>
  </div>
  <default-card class="centered"/>
</div>
</template>

<script>
import card from "./Card";
import defaultCard from "./DefaultCard";
export default {
  name: "GameCards",
  components: {
    card,
    defaultCard
  },
  data() {
    return {
      cardSelect: '',
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
  },
  methods: {
    selectedCard(card) {
      this.cardSelect = card.name;
    }
  }
}
</script>

<style scoped>
.game-cards {
  margin: 120px auto 64px;
  max-width: 1163px;
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
  margin-top: 32px;
}

.card {
  margin: 0 12px;
}
.card.selected-card {
  box-shadow: 0px 0px 13px 0px #0CECDD;
}
.centered {
  margin: 0 auto;
}
</style>