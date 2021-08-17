<template>
  <div class="time">
    <template>
      <button v-if="this.interval == ''" @click="start">启动</button>
      <button v-else @click="stop">停止</button>
    </template>
    <template>
      <button v-if="$parent.timeArr.length >= 1 && this.interval == ''" @click="rest">复位</button>
      <button v-else  @click="timeCount">计次</button>
    </template>
    
  </div>
</template>
<script>
export default {
  name: 'control-buttons',
  props: {
    time: {
      type: Number,
      defalt:0
    }
  },
  data () {
    return {
      interval: '',
    }
  },
  methods: {
    start () {
      this.interval = setInterval(() => {
        // this.time += 1
        this.$emit('setTime',this.$parent.time + 10)
      },10)
    },
    stop () {
      clearInterval(this.interval)
      this.interval = ''
    },
    rest () {
      // this.time = 0
      this.$emit('setTime', 0)
    },
    timeCount () {
      // return this.time
      this.$emit('timeCount')
    }
  },
}
</script>

<style scoped lang="scss">
.time{
  display: flex;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box;
  justify-content: space-between;
}
button{
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: 0;
  background-color: gray;
}
</style>
