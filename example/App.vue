<template>
  <div id="app">
    <vm-menu>
      hello world
    </vm-menu>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      data: 'Hello world'
    }
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
</style>
