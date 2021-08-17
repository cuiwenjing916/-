<template>
  <div id="app">
    <div class="box">
      <major-clock :time='time' />
      <control-buttons
      :time='time'
      @setTime='setTime'
      @timeCount="timeCount"
      />
      <split-times :times="timeArr"/>
    </div>
    <footer-bar />
  </div>
</template>

<script>
import footerBar from './components/footerBar.vue'
import MajorClock from './components/MajorClock.vue'
import ControlButtons from './components/ControlButtons.vue'
import SplitTimes from './components/SplitTimes.vue'

export default {
  name: 'App',
  components: {
    footerBar,
    MajorClock,
    ControlButtons,
    SplitTimes
  },
  data () {
    return {
      time: 0,
      timeArr: []
    }
  },
  methods: {
    setTime (time) {
      this.time = time
    },
    timeCount () {
      this.timeArr.push(this.time)
    }
  },
}
</script>

<style lang="scss">
body{
  margin: 0;
  padding: 0;
}
*{
  margin: 0;
  padding: 0;
  list-style: none;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  .box{
    width: 100%;
    min-height: 100vh;
    background-color: #000;
    flex: 1;
  }
}
</style>
