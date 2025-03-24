<template>
  <div class="background" :style="{ '--bg-image': `url(${imageUrl})` }">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Background',
  props: {
    imageUrl: {
      type: String,
      default: 'https://images.unsplash.com/photo-1707343843437-caacff5cfa74?q=80&w=1920&auto=format'
    }
  }
}
</script>

<style scoped>
.background {
  min-height: 100vh;
  width: 100%;
  background-image: var(--bg-image);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>
