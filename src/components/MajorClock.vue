<template>
  <div class="time" v-html="formatTime">
    
  </div>
</template>

<script>
export default {
  name: 'major-clock',
  props: {
    time: {
      type: Number,
      defalt:0
    }
  },
  computed: {
    formatTime () {
      var s = Math.floor(this.time / 1000)
      var m = Math.floor(this.time % 1000) / 10
      var f = Math.floor(this.time / (1000 * 60))
      s = s <10 ? '0' + s : s
      m = m <10 ? '0' + m : m
      f = f <10 ? '0' + f : f
      return `<span>${f}</span>:<span>${s}</span>.<span>${m}</span>`
    }
  }
}
</script>
<style scoped lang="scss">
.time{
  color: #fff;
  font-size: 80px;
  padding: 80px 0;
  /deep/span{
    display: inline-block;
    width: 80px;
    padding: 5px 0;
  }
}
</style>
