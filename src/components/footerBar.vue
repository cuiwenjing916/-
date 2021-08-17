<template>
  <nav class="footer">
    <ul>
      <li>
        <i>🧭</i>
        <span>世界时钟</span>
      </li>
      <li>
        <i>🧭</i>
        <span>闹铃</span>
      </li>
      <li>
        <i>🧭</i>
        <span>秒表</span>
      </li>
      <li>
        <i>🧭</i>
        <span>计时器</span>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'footer-bar',
}
</script>

<style scoped lang="scss">
.footer {
  width: 100%;
  height: 60px;
  background-color: #333;
  position: fixed;
  bottom: 0;
  ul{
    display: flex;
    align-items: center;
    justify-content: space-between;
    li{
      flex: 1;
      font-size: 14px;
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      i{
        font-size: 20px;
        margin: 10px 0;
      }
    }
  }
}
</style>