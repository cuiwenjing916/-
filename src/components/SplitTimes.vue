<template>
  <div>
    <ul class="list">
      <li v-for="(item,index) in times" :key="index">
        <span>{{index + 1}} </span>
        <!-- <span>{{formatTime(item)}}</span> -->
        <span>{{item | formatTime}}</span>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'split-times',
  props: {
    times: {
      type:Array,
      default: () => []
    }
  },
  filters: {
    formatTime (time) {
      var s = Math.floor(time / 1000)
      var m = Math.floor(time % 1000) / 10
      var f = Math.floor(time / (1000 * 60))
      s = s <10 ? '0' + s : s
      m = m <10 ? '0' + m : m
      f = f <10 ? '0' + f : f
      return `${f}:${s}.${m}`
    }
  }
  /* methods: {
    formatTime (time) {
      var s = Math.floor(time / 1000)
      var m = Math.floor(time % 1000) / 10
      var f = Math.floor(time / (1000 * 60))
      s = s <10 ? '0' + s : s
      m = m <10 ? '0' + m : m
      f = f <10 ? '0' + f : f
      return `${f}:${s}.${m}`
    }
  }, */
}
</script>

<style scoped lang="scss">
.list{
  width: 100%;
  color: #fff;
  li{
    display: flex;
    padding: 5px 10px;
    box-sizing: border-box;
    justify-content: space-between;
  }
}
</style>