<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img :src="item.imgUrl" class="item-img"/>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
          <div class="item-button">查看详情</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    line-height .8rem
    background #eee
    text-indent .2rem
    margin-top .2rem
    text-align: left;
  .item
    display flex
    height 1.9rem
    overflow hidden
    text-align left
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        height .4rem
        color #eee
        ellipsis()
      .item-button
        width 1.3rem
        line-height .44rem
        margin-top .16rem
        color #fff
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        cursor pointer
</style>
