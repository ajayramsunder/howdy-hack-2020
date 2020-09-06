<template>
  <div id="app">
    <map-widget/>
    <decoder/>
  </div>
</template>

<script>
import MapWidget from './components/InitialMap.vue'
import Decoder from './components/Decoder.vue'
export default {
  name: 'App',
  components: {
    MapWidget,
    Decoder
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: inline;
}
</style>
