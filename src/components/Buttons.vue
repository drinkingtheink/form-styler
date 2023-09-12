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
    inputPadding: String,
  },
  computed: {
      btnStyles() {
          return {
              'borderRadius': `${this.borderRadius}px`,
              'padding': `${this.inputPadding}px`,
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
