<template>
  <div class="image-wrapper" @click="showAnswer">
    <transition name="flip">
      <img key="question" v-if="show === false" src="../src/assets/question.png" alt="question">
      <img key="answer" v-else :src="`..${answerCard.source}`" :alt="answerCard.name">
    </transition>
  </div>
</template>

<script>
export default {
  name: "DefaultCard",
  props: {
    answerCard: Object,
  },
  data() {
    return {
      show: false,
    }
  },
  methods: {
    showAnswer() {
      this.show = !this.show;
      this.$emit("answer");
    }
  }
}
</script>

<style scoped>
.image-wrapper {
  max-width: 210px;
  max-height: 210px;
  border-radius: 8px;
  /*border: 1px solid #664E88;*/
  cursor: pointer;
  margin-top: 32px;
  /*box-shadow: 0px 9px 55px #666;*/
}

.image-wrapper:hover {
  /*box-shadow: 0px 0px 13px 0px rgba(102,78,136,1);*/
  max-width: 220px;
  max-height: 220px;
  transition: all 0.4s;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  border-radius: 8px;
}

.flip-enter-active {
  transition: all 0.4s ease;
}

.flip-leave-active {
  display: none;
}

.flip-enter, .flip-leave {
  transform: rotateY(180deg);
  opacity: 0;

}

</style>