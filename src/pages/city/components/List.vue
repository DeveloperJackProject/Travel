<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.getCurrentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div
            class="button-wrapper"
            v-for="item of hotCities"
            :key="item.id"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div
        class="area"
        v-for="(item, key) of cities"
        :key="key"
      >
        <div class="title border-topbottom">{{key}}</div>
        <div
          class="item-list"
          v-for="cItem of item"
          :key="cItem.id"
        >
          <div class="item border-bottom">{{cItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    currentCity: Object,
    hotCities: Array,
    cities: Object
  },
  computed: {
    getCurrentCity () {
      return this.currentCity.name
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  updated () {
    this.scroll.refresh()
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .border-topbottom
    &:before
      border-color #ccc
    &:after
      border-color #ccc
  .list
    position absolute
    overflow hidden
    top 1.6rem
    left 0
    right 0
    bottom 0
    .title
      line-height .44rem
      font-size .26rem
      background #eee
      padding-left .2rem
      color #666
      text-align left
    .button-list
      padding .1rem .6rem .1rem .1rem
      overflow hidden
      .button-wrapper
        width 33.3%
        float left
        .button
          margin .1rem
          padding .1rem 0
          text-align center
          border .02rem solid #ccc
          box-sizing border-box
    .item-list
      .item
        line-height .76rem
        padding-left .2rem
        text-align left
      .border-bottom
        &:before
          border-color #ccc
</style>
