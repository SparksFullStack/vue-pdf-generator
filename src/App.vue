<template>
  <div id="app">
    <PdfInput />  
  </div>
</template>

<script>
import PdfInput from './components/PdfInput.vue'

export default {
  name: 'app',
  components: {
    PdfInput
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
