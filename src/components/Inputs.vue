<template>
  <div class="input-collection">
      <h2>Inputs</h2>

      <section>
        <label for="text-input-exanmple">Text Input Example:</label>
        <input 
            id="text-input-example" 
            type="text" 
            placeholder="An Example Text Input"
        />
      </section>

      <section>
        <label for="textarea-input-exanmple">Textarea Input Example:</label>
        <textarea 
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
}
</script>

<style>
section {
    margin: 1rem 0;
}

input, textarea {
    border-color: var(--primary) !important;
    padding: var(--inputHorPadding)px var(--inputVertPadding)px;
}
</style>
