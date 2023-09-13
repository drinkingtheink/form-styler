<template>
  <div class="colors-collection">
      <h2>Colors</h2>

        <div class="color-swatch primary" />
        <div class="color-swatch secondary" />
  </div>
</template>

<script>
export default {
  name: 'Colors',
  props: {
      primary: String,
      secondary: String,
  }
}
</script>

<style scoped>

</style>
