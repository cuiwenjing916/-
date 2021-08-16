<template>
  <div id="app">
    <major-clock />
    <!-- <control-buttons />   -->
    <!-- <split-times /> -->
  </div>
</template>

<script>
// import splitTimes from './components/SplitTimes.vue'
import majorClock from './components/MajorClock.vue'
// import ControlButtons from './components/ControlButtons.vue'

export default {
  name: 'App',
  components: {
    majorClock,
    // ControlButtons,
    // splitTimes
  }
}
</script>

<style>
#app {
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
