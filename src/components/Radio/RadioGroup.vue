<template>
  <div :class="className">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'al-radio-group',
  props: {
    value: {
      default: ''
    },
    disabled: Boolean
  },
  data () {
    return {
      val: this.value
    }
  },
  watch: {
    val (newValue) {
      this.$emit('input', newValue)
    },
    value (newValue) {
      this.val = newValue
    }
  },
  computed: {
    className () {
      return {
        disabled: this.disabled
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.disabled {
  opacity: 0.8;
  color: #ccc;

}
</style>
