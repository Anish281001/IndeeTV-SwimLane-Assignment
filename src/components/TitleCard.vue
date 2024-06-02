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

</style>