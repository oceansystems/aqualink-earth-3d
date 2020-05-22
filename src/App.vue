<template>
  <div id="app">
    <Map/>
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
html, body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100%;
  margin: 0;
}
</style>
