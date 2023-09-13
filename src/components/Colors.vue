<template>
  <div class="colors-collection">
    <h2>Colors</h2>

    <section>
        <div class="color-swatch primary">Primary</div>
        <div class="color-swatch secondary">Secondary</div>
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

.primary {
    background-color: var(--primary);
}

.secondary {
    background-color: var(--secondary);
}
</style>
