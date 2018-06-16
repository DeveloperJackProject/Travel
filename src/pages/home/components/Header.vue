<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-fanhui"></span>
    </div>
    <div class="header-input"><span class="iconfont icon-sousuo"></span>输入经典/城市/游玩/主题</div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <span class="iconfont icon-jiantou"></span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    height: $headerHeight
    line-height: $headerHeight
    display: flex
    background-color: $bgColor
    color: #fff
    .header-left
      width: .64rem
    .header-input
      flex:1
      height .64rem
      line-height .64rem
      margin .12rem 0 0 .2rem
      background-color #fff
      border-radius .1rem
      color #cccccc
    .header-right
      width: 1.24rem
      text-align center
      color #fff
      .icon-jiantou
        font-size .24rem
</style>
