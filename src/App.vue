<template>
  <div id="app">
    <al-button type="warning" text @click="eventClick">点击</al-button>

    <al-radio-group v-model="sex">
      <al-radio :value="1">男</al-radio>
      <al-radio :value="0">女</al-radio>
    </al-radio-group>

    <al-radio-group v-model="lianxi" disabled>
      <al-radio :value="1">父亲</al-radio>
      <al-radio :value="2">母亲</al-radio>
      <al-radio :value="3">兄弟</al-radio>
      <al-radio :value="4">妻子</al-radio>
      <al-radio :value="5">儿子</al-radio>
      <al-radio :value="6">爷爷</al-radio>
    </al-radio-group>
  </div>
</template>

<script>
import AlButton from './components/Button'
import Radio from './components/Radio'

export default {
  name: 'App',
  components: {
    AlButton,
    AlRadio: Radio.AlRadio,
    AlRadioGroup: Radio.AlRadioGroup
  },
  data () {
    return {
      sex: 0,
      lianxi: ''
    }
  },
  methods: {
    eventClick () {
      alert(1)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
