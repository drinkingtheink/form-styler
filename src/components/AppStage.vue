<template>
  <main>
    <h1>Form Styler</h1>

    <div class="left-pane controls">
      <h2>Settings:</h2>

      <input @change="handleBorderRadiusUpdate" type="range" id="borderRadiusInput" name="borderRadiusInput" min="0" max="100" />
      <label for="borderRadiusInput">Border Radius</label>

      <input @change="handleInputPaddingUpdate" type="range" id="borderRadiusInput" name="borderRadiusInput" min="0" max="100" />
      <label for="borderRadiusInput">Padding</label>
    </div>

    <div class="right-pane">
      <Inputs 
        :borderColor="borderColor" 
        :borderRadius="borderRadius" 
        :borderWidth="borderWidth"
        :inputPadding="inputPadding"
      />
    </div>
  </main>
</template>

<script>
import Inputs from './Inputs.vue'

export default {
  name: 'AppStage',
  props: {
    msg: String
  },
  components: {
    Inputs
  },
  data() {
    return {
      borderRadius: 0,
      borderWidth: 0,
      borderColor: 0,
      inputPadding: 0,
    }
  },
  methods: {
    handleBorderRadiusUpdate(e) {
      this.borderRadius = e.target.value;
    },
    handleInputPaddingUpdate(e) {
      this.inputPadding = e.target.value;
    },
  }
}
</script>

<style scoped>
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
