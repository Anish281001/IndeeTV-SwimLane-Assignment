<template>
  <div class="title-card" tabindex="0">
    <img :src="image" :alt="title" />
    <div class="title">{{ title }}</div>
  </div>
</template>

<script>
export default {
  name: 'TitleCard',
  props: {
    title: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.title {
  margin-top: 10px;
  font-size: 1em;
  font-weight: bold;
}

.title-card {
  height: 200px;
  margin-left: 32px;
}
.title-card:hover {
  transform: scale(1.2); 
  z-index: 2; 
   outline: 2px solid rgb(230, 77, 77); 
}

.title-card:hover ~ .title-card,
.title-card:hover ~ .title-card + .title-card {
  filter: brightness(0.5); /* Darken effect */
  /* Or use filter: blur(3px); for blur effect */
}
.title-card:hover ~ .title-card ~ .title-card,
.title-card:hover ~ .title-card ~ .title-card + .title-card {
  filter: brightness(0.5); /* Darken effect */
  /* Or use filter: blur(3px); for blur effect */
}
</style>