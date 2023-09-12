<template>
  <div class="input-collection">
      <h2>Inputs</h2>

      <section>
        <label for="text-input-exanmple">Text Input Example:</label>
        <input 
            :style="inputStyles" 
            id="text-input-example" 
            type="text" 
            placeholder="An Example Text Input"
        />
      </section>

      <section>
        <label for="textarea-input-exanmple">Textarea Input Example:</label>
        <textarea 
            :style="inputStyles" 
            id="textarea-input-example" 
            type="text" 
            placeholder="An Example Text Input" 
        />
      </section>
  </div>
</template>

<script>
export default {
  name: 'Inputs',
  props: {
    borderRadius: String,
    borderWidth: String,
    borderColor: String,
    inputPadding: String,
  },
  computed: {
      inputStyles() {
          return {
              'borderRadius': `${this.borderRadius}px`,
              'padding': `${this.inputPadding}px`,
          }
      }
  }
}
</script>

<style lang="scss">


</style>
