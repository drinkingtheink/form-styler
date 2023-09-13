<template>
  <main>
    <div class="left-pane controls">
      <h2>Settings:</h2>

      <h3>Colors</h3>

      <section class="control-group">
        <div>
          <input 
            @input="handlePrimaryColorUpdate"
            type="color" 
            id="primaryColorInput" 
            name="primaryColorInput" 
          />
          <label for="primaryColorInput">Primary</label>
        </div>

        <div>
          <input 
            @input="handleSecondaryColorUpdate"
            type="color" 
            id="secondaryColorInput" 
            name="secondaryColorInput" 
            value="#ffffff"
          />
          <label for="secondaryColorInput">Secondary</label>
        </div>
      </section>

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
      <label for="borderRadiusInput"><strong>{{ borderRadius }}</strong> Border Radius</label>

      <input 
        @input="handleInputHorPaddingUpdate" 
        type="range" 
        id="horPaddingInput" 
        name="horPaddingInput" 
        min="0" 
        max="500" 
        value="5"
      />
      <label for="horPaddingInput"><strong>{{ inputHorPadding }}</strong> Horizontal Padding</label>

      <input 
        @input="handleInputVertPaddingUpdate" 
        type="range" 
        id="vertPaddingInput" 
        name="vertPaddingInput" 
        min="0" 
        max="500" 
        value="10"
      />
      <label for="vertPaddingInput"><strong>{{ inputVertPadding }}</strong> Vertical Padding</label>

      <input 
        @input="handleInputBorderWidthUpdate" 
        type="range" 
        id="inputBorderWidthInput" 
        name="inputBorderWidthInput" 
        min="0" 
        max="50" 
        value="10"
      />
      <label for="inputBorderWidthInput"><strong>{{ inputBorderWidth }}</strong> Border Width</label>
    
      <h3>Buttons</h3>

      <input 
        @input="handleBtnBorderRadiusUpdate" 
        type="range" 
        id="btnBorderRadiusInput" 
        name="btnBorderRadiusInput" 
        min="0" 
        max="500"
        value="10"
      />
      <label for="btnBorderRadiusInput"><strong>{{ btnBorderRadius }}</strong> Border Radius</label>

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

      <Colors />

      <Inputs 
        :borderRadius="borderRadius" 
        :borderWidth="inputBorderWidth"
        :inputHorPadding="inputHorPadding"
        :inputVertPadding="inputVertPadding"
      />

      <Buttons 
        :borderRadius="borderRadius" 
        :borderWidth="btnBorderWidth"
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
      btnBorderRadius: 0,
      color: {
        primary: null,
        secondary: null,
      }
    }
  },
  methods: {
    handleBorderRadiusUpdate(e) {
      this.borderRadius = `${e.target.value}px`;
      document.documentElement.style.setProperty('--inputBorderRadius', `${e.target.value}px`);
    },
    handleInputHorPaddingUpdate(e) {
      this.inputHorPadding = `${e.target.value}px`;
      document.documentElement.style.setProperty('--inputHorPadding', `${e.target.value}px`);
    },
    handleInputVertPaddingUpdate(e) {
      this.inputVertPadding = `${e.target.value}px`;
      document.documentElement.style.setProperty('--inputVertPadding', `${e.target.value}px`);
    },
    handleBtnHorPaddingUpdate(e) {
      this.btnHorPadding = `${e.target.value}px`;
      document.documentElement.style.setProperty('--btnHorPadding', `${e.target.value}px`);
    },
    handleBtnVertPaddingUpdate(e) {
      this.btnVertPadding = `${e.target.value}px`;
      document.documentElement.style.setProperty('--btnVertPadding', `${e.target.value}px`);
    },
    handleBtnBorderRadiusUpdate(e) {
      this.btnBorderRadius = `${e.target.value}px`;
      document.documentElement.style.setProperty('--btnBorderRadius', `${e.target.value}px`);
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
  text-align: right;
  padding-right: 1rem;
}

.control-group {
  display: flex;
  justify-content: flex-end;
}

.control-group div {
  margin-left: 20px;
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
