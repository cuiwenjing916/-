<template>
  <div id="time">
    <div class="header">
      <div class="head">
        <span>00:</span>
        <span>00:</span>
        <span v-html="val">00</span>
      </div>
      <div class="box">
        <button @click="start">开始</button>
        <button @click="stop">停止</button>
      </div>
    </div>
    <div class="footer">
      <ul>
        <li v-for="(item,index) in list" :key="index"
        :class="{active: activeIndex === index} "
        >
          {{item}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: Number,
      default: 0
    }
  },
  data () {
    return {
      val: this.value,
      countTime : null,
      data: new Date(),
      list:[
        '世界时钟',
        '闹铃',
        '秒表',
        '计时器'
      ],
      activeIndex: 2
    }
  },
  /* computed: {
    star (dtat) {
      d=Math.floor(this.data/1000/60/60/24),
      h=Math.floor(this.data/1000/60/60%24),
      m=Math.floor(this.data/1000/60%60),
      s=Math.floor(this.data/1000%60)
    }
  }, */
  methods: {
    start () {
      this.counTime = setInterval(() => {
        this.val++
        if (this.val === 60){
          this.val = 0
        }
        // this.val = this.data.toLocaleTimeString()
      }, 100);
    },
    stop () {
      clearInterval(this.countTime)
    }
  },
}
</script>

<style scoped>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#time{
  width: 100%;
  height: 100%;
  background-color: #000;
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: space-between
}
.header{
  width: 100%;
  flex: 1;
}
.head{
  color: #fff;
  font-size: 80px;
  padding: 120px 0;
}
.box{
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 10px;
}
.box button{
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: 0;
  background-color: gray;
}
.footer{
  width: 100%;
  height: 80px;
}
.footer ul{
  width: 100%;
  display: flex;
  justify-content: space-around;
  list-style: none;
}
.footer ul .active{
  color: rgba(255, 0, 0, 0.856);
}
</style>