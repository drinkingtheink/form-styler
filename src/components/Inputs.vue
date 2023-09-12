<template>
  <div class="input-collection">
      <h2>Inputs</h2>

      <section>
        <label for="text-input-exanmple">Text Input Example:</label>
        <input id="text-input-example" type="text" placeholder="An Example Text Input" />
      </section>

      <section>
        <label for="textarea-input-exanmple">Textarea Input Example:</label>
        <textarea id="textarea-input-example" type="text" placeholder="An Example Text Input" />
      </section>
  </div>
</template>

<script>
export default {
  name: 'Inputs'
}
</script>

<style >
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
