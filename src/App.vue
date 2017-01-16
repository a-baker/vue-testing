<template>
  <div id="app">
    <h1>Vue.js testing</h1>
    <messagebox></messagebox>
  </div>
</template>

<script>
import Hello from './components/Hello'
import messagebox from './components/MessageBox'

export default {
  name: 'app',
  components: {
    messagebox
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
  margin-top: 60px;
}

h1 {
  color: #258474;
}
</style>
