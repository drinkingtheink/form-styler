<template>
  <main>
    <div class="left-pane controls">
      <h2>Settings:</h2>

      <h3>Colors</h3>
      <input 
        @input="handlePrimaryColorUpdate"
        type="color" 
        id="primaryColorInput" 
        name="primaryColorInput" 
      />
      <label for="primaryColorInput">Primary</label>

      <input 
        @input="handleSecondaryColorUpdate"
        type="color" 
        id="secondaryColorInput" 
        name="secondaryColorInput" 
      />
      <label for="secondaryColorInput">Secondary</label>

      <h3>Inputs</h3>
      <input 
        @input="handleBorderRadiusUpdate" 
        type="range" 
        id="borderRadiusInput" 
        name="borderRadiusInput" 
        min="0" 
        max="100" 
        value="2"
      />
      <label for="borderRadiusInput"><strong>{{ borderRadius }}%</strong> Border Radius</label>

      <input 
        @input="handleInputHorPaddingUpdate" 
        type="range" 
        id="horPaddingInput" 
        name="horPaddingInput" 
        min="0" 
        max="500" 
        value="5"
      />
      <label for="horPaddingInput"><strong>{{ inputHorPadding }}px</strong> Horizontal Padding</label>

      <input 
        @input="handleInputVertPaddingUpdate" 
        type="range" 
        id="vertPaddingInput" 
        name="vertPaddingInput" 
        min="0" 
        max="500" 
        value="10"
      />
      <label for="vertPaddingInput"><strong>{{ inputVertPadding }}px</strong> Vertical Padding</label>

      <input 
        @input="handleInputBorderWidthUpdate" 
        type="range" 
        id="inputBorderWidthInput" 
        name="inputBorderWidthInput" 
        min="0" 
        max="50" 
        value="10"
      />
      <label for="inputBorderWidthInput"><strong>{{ inputBorderWidth }}px</strong> Border Width</label>
    
      <h3>Buttons</h3>

      <input 
        @input="handleBtnHorPaddingUpdate" 
        type="range" 
        id="btnHorPaddingInput" 
        name="btnHorPaddingInput" 
        min="0" 
        max="500" 
        value="50"
      />
      <label for="btnHorPaddingInput"><strong>{{ btnHorPadding }}px</strong> Horizontal Padding</label>
      
      
      <input 
        @input="handleBtnVertPaddingUpdate" 
        type="range" 
        id="btnVertPaddingInput" 
        name="btnVertPaddingInput" 
        min="0" 
        max="500"
        value="10"
      />
      <label for="btnVertPaddingInput"><strong>{{ btnVertPadding }}px</strong> Vertical Padding</label>
    </div>

    <div class="right-pane">
      <h1>Elements</h1>

      <Colors 
        :primary="color.primary"
        :secondary="color.secondary"
      />

      <Inputs 
        :borderRadius="borderRadius" 
        :borderWidth="inputBorderWidth"
        :inputHorPadding="inputHorPadding"
        :inputVertPadding="inputVertPadding"
      />

      <Buttons 
        :borderRadius="borderRadius" 
        :borderWidth="borderWidth"
        :btnHorPadding="btnHorPadding"
        :btnVertPadding="btnVertPadding"
      />
    </div>
  </main>
</template>

<script>
import Inputs from './Inputs.vue'
import Buttons from './Buttons.vue'
import Colors from './Colors.vue'

export default {
  name: 'AppStage',
  components: {
    Inputs,
    Buttons,
    Colors,
  },
  data() {
    return {
      borderRadius: 2,
      inputBorderWidth: 5,
      inputHorPadding: 5,
      inputVertPadding: 10,
      btnHorPadding: 50,
      btnVertPadding: 10,
      color: {
        primary: null,
        secondary: null,
      }
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
    handleBtnHorPaddingUpdate(e) {
      this.btnHorPadding = e.target.value;
    },
    handleBtnVertPaddingUpdate(e) {
      this.btnVertPadding = e.target.value;
    },
    handlePrimaryColorUpdate(e) {
      this.color.primary = e.target.value;
      document.documentElement.style.setProperty('--primary', e.target.value);
    },
    handleSecondaryColorUpdate(e) {
      this.color.secondary = e.target.value;
      document.documentElement.style.setProperty('--secondary', e.target.value);
    },
    handleInputBorderWidthUpdate(e) {
      this.inputBorderWidth = e.target.value;
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

.controls input {
  margin-top: 1rem;
}
</style>
