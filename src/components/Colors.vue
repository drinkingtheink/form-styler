<template>
  <div class="colors-collection">
    <h2>Colors</h2>

    <section>
        <div :style="primaryStyles" class="color-swatch primary">Primary</div>
        <div :style="secondaryStyles" class="color-swatch secondary">Secondary</div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Colors',
  props: {
      primary: String,
      secondary: String,
  },
  computed: {
      primaryStyles() {
          return {
              'backgroundColor': `${this.primary}`
          }
      },
      secondaryStyles() {
          return {
              'backgroundColor': `${this.secondary}`
          }
      },
  }
}
</script>

<style scoped>
section {
    display: flex;
}

.color-swatch {
    width: 30%;
    padding: 2rem;
    margin-right: 10px;
    border: 5px solid rgba(0,0,0,0.2);
}
</style>
