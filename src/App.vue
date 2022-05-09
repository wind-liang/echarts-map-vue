<template>
  <div id="app">
    <Map msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Map from './components/Map.vue'

export default {
  name: 'App',
  components: {
    Map,
  }
}
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh;
}
</style>
