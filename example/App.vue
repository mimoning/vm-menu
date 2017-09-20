<template>
  <div id="app">
    <vm-menu>
      hello world
      <div slot="menu">1121212</div>
    </vm-menu>
    <vm-menu>
      hello world
      <div slot="menu">
        <ul>
          <li>1. 1111</li>
          <li>2. 2222</li>
          <li>3. 3333</li>
          <li>4. 4444</li>
          <li>5. 5555</li>
        </ul>
      </div>
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
