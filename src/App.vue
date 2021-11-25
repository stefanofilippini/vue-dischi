<template>
  <div id="app">
    <Discs/>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Discs from './components/Discs'
import 'bootstrap/dist/css/bootstrap.min.css'

export default {
  name: 'App',
  components: {
    Discs,
//    HelloWorld
  },
}
</script>

<style lang="scss">
body {
  background-color: #1d2d3c;
}

</style>
