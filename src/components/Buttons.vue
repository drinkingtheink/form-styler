<template>
  <div class="buttons-collection">
      <h2>Buttons</h2>

      <section class="buttons-gallery">
        <button :style="btnStyles">Check It Out</button>
      </section>
  </div>
</template>

<script>
export default {
  name: 'Buttons',
  props: {
    borderRadius: String,
    borderWidth: String,
    btnHorPadding: String,
    btnVertPadding: String,
  },
  computed: {
      btnStyles() {
          return {
              'borderRadius': `${this.borderRadius}%`,
              'padding': `${this.btnVertPadding}px ${this.btnHorPadding}px`,
          }
      }
  }
}
</script>

<style>
.buttons-gallery {
    margin: 1rem 0;
}

button {
    background-color: var(--primary);
    color: var(--secondary);
}
</style>
