<template>
  <div class="buttons-collection">
      <h2>Buttons</h2>

      <section>
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
    borderColor: String,
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

<style scoped>
section {
    margin: 1rem 0;
}

</style>
