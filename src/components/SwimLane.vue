<template>
  <div :class="['block', className]">
    <div class="swim-lane__header">{{ header }}</div>
    <div class="swim-lane">
      <div class="controls">
        <button class="left" @click="scrollLeft" aria-label="Scroll left" :disabled="atStart"  aria-controls="swim-lane-container">&lt;</button>
        <button class="right" @click="scrollRight" aria-label="Scroll right" :disabled="atEnd"  aria-controls="swim-lane-container">&gt;</button>
      </div>
      <div class="swim-lane__container" :style="{ transform: `translateX(-${scrollPosition}px)` }" tabindex="0" role="region" aria-label="Swim lane">
        <TitleCard
          v-for="(card, index) in cards"
          :key="index"
          :title="card.title"
          :image="card.image"
        />
      </div>
    </div>
  </div>
</template>

<script>
import TitleCard from './TitleCard.vue';

export default {
  name: 'SwimLane',
  components: {
    TitleCard
  },
  props: {
    header: {
      type: String,
      required: true
    },
    cards: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      scrollPosition: 0,
      cardWidth: 240, 
      containerWidth: 0 
    };
  },
  computed: {
    atStart() {
      return this.scrollPosition === 0;
    },
    atEnd() {
      const totalWidth = this.cards.length * this.cardWidth;
      return this.scrollPosition + this.containerWidth >= totalWidth;
    }
  },
  methods: {
    scrollLeft() {
      this.scrollPosition = this.scrollPosition - this.containerWidth;
    },
    scrollRight() {
      const totalWidth = this.cards.length * this.cardWidth;
      const maxScrollPosition = totalWidth - this.containerWidth;
      this.scrollPosition = this.scrollPosition + this.containerWidth, maxScrollPosition;
    },
    updateContainerWidth() {
      this.containerWidth = this.$el.offsetWidth;
    }
  },
   handleKeydown(event) {
      if (event.key === 'ArrowLeft') {
        this.scrollLeft();
      } else if (event.key === 'ArrowRight') {
        this.scrollRight();
      }
    },
  mounted() {
    this.updateContainerWidth();
    window.addEventListener('resize', this.updateContainerWidth);  
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateContainerWidth);
  }
};
</script>

<style scoped>
.block{
  margin-top: 50px;
}
.swim-lane__header{
  margin-left: 30px;
  margin-top: 30px;
  font-size: 30px;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
@media screen and (max-width: 480px){
  .swim-lane__header{
    font-size: 8px;
  }
}

</style>
