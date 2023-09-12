<template>
  <main>
    <h1>Form Styler</h1>

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

<style lang="scss">

</style>
