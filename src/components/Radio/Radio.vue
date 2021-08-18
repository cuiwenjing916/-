<template>
  <label class="radio-item">
    <input type="radio" :value="value" v-model="$parent.val" :disabled="$parent.disabled" />
    <div>
      <slot></slot>
    </div>
  </label>
</template>

<script>
export default {
  name: 'al-radio',
  props: {
    value: {}
  }
}
</script>

<style lang="scss" scoped>
.radio-item {
  margin-right: 10px;
  input {
    display: none;
    & + div {
      display: inline-block;
      &::before {
        content: "";
        display: inline-block;
        border: 1px solid #dcdfe6;
        border-radius: 100%;
        width: 14px;
        height: 14px;
        background-color: #fff;
        position: relative;
        cursor: pointer;
        display: inline-block;
        box-sizing: border-box;
        margin-right: 5px;
      }
    }
    &:checked + div{
      color: #409eff;
      &::before {
        border-color: #409eff;
        border-width: 4px;
        box-sizing: border-box;
      }
    }
  }
}
</style>
