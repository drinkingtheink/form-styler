<template>
  <main>
    <div class="left-pane controls">
      <h2>Settings:</h2>

      <input 
        @input="handleBorderRadiusUpdate" 
        type="range" 
        id="borderRadiusInput" 
        name="borderRadiusInput" 
        min="0" 
        max="50" 
        value="10"
      />
      <label for="borderRadiusInput">Border Radius</label>

      <input 
        @input="handleInputPaddingUpdate" 
        type="range" 
        id="borderRadiusInput" 
        name="borderRadiusInput" 
        min="0" 
        max="100" 
        value="10"
      />
      <label for="borderRadiusInput">Padding</label>
    </div>

    <div class="right-pane">
      <h1>Elements</h1>

      <Inputs 
        :borderColor="borderColor" 
        :borderRadius="borderRadius" 
        :borderWidth="borderWidth"
        :inputPadding="inputPadding"
      />

      <Buttons 
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
import Buttons from './Buttons.vue'

export default {
  name: 'AppStage',
  props: {
    msg: String
  },
  components: {
    Inputs,
    Buttons,
  },
  data() {
    return {
      borderRadius: 10,
      borderWidth: 0,
      borderColor: 0,
      inputPadding: 10,
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

<style>
main {
  display: flex;
}

.left-pane {
  width: 30%;
  max-width: 400px;
}

.right-pane {
  padding-left: 2rem;
  border-left: 1px solid;
  height: 100vh;
}
</style>
