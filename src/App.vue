<template>
  <AppStage />
</template>

<script>
import AppStage from './components/AppStage.vue'

export default {
  name: 'App',
  components: {
    AppStage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 20px;
}

label {
  display: block;
}

input[type=text], textarea {
  min-width: 300px;
}

:root {
  --primary: #000000;
  --secondary: #ffffff;
  --inputBorderRadius: 10px;
  --inputBorderWidth: 5px;
  --inputHorPadding: 10px;
  --inputVertPadding: 5px;
  --inputBorderWidth: 5px;
  --btnBorderRadius: 5px;
  --btnHorPadding: 20px;
  --btnVertPadding: 10px;
}
</style>
