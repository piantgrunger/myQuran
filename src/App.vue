<template>
  <div id="app">
      <quranku></quranku>
  </div>
</template>

<script>
import Quranku from './components/Quranku'


export default {
  name: 'app',
  components: {
    Quranku
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
