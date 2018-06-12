<template>
  <div class="header">
    <div class="header-left">返回</div>
    <div class="header-input">城市</div>
    <div class="header-right">内容</div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    height: .86rem
    display: flex
    background-color: #00bcd4
    color: #fff
    .header-left
      width: .64rem
    .header-input
      flex:1
    .header-right
      width: 1.24rem
</style>
