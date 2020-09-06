<template>
  <div id="app">
    <map-widget v-bind:truthvalue="truthValue"/>
    <drop-down/>
    <decoder @input="propAssignment"/>
    <title-bar/>
  </div>
</template>

<script>
import MapWidget from './components/InitialMap.vue'
import DropDown from './components/DropDown.vue'
import TitleBar from './components/TitleBar.vue'
export default {
  name: 'App',
  components: {
    MapWidget,
    DropDown,
    TitleBar
  },
  methods:{
    propAssignment(e){
      this.truthValue = e 
    }
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
