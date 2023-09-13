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
        max="100" 
        value="10"
      />
      <label for="borderRadiusInput"><strong>{{ borderRadius }}px</strong> Border Radius</label>

      <input 
        @input="handleInputHorPaddingUpdate" 
        type="range" 
        id="horPaddingInput" 
        name="horPaddingInput" 
        min="0" 
        max="100" 
        value="10"
      />
      <label for="horPaddingInput"><strong>{{ inputHorPadding }}px</strong> Horizontal Padding</label>

      <input 
        @input="handleInputVertPaddingUpdate" 
        type="range" 
        id="vertPaddingInput" 
        name="vertPaddingInput" 
        min="0" 
        max="100" 
        value="10"
      />
      <label for="vertPaddingInput"><strong>{{ inputVertPadding }}px</strong> Vertical Padding</label>
    </div>

    <div class="right-pane">
      <h1>Elements</h1>

      <Inputs 
        :borderColor="borderColor" 
        :borderRadius="borderRadius" 
        :borderWidth="borderWidth"
        :inputHorPadding="inputHorPadding"
        :inputVertPadding="inputVertPadding"
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
      inputHorPadding: 10,
      inputVertPadding: 10,
    }
  },
  methods: {
    handleBorderRadiusUpdate(e) {
      this.borderRadius = e.target.value;
    },
    handleInputHorPaddingUpdate(e) {
      this.inputHorPadding = e.target.value;
    },
    handleInputVertPaddingUpdate(e) {
      this.inputVertPadding = e.target.value;
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
