<template>
  <div class="icons">
    <swiper :options="swiperOption" v-if="showIcon">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icons-image">
            <img class="icon-image-content" :src="item.imgUrl">
          </div>
          <p class="icon-dsc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    },
    showIcon () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%
  .icons
    margin-top .1rem
    .icon
      float left
      width 25%
      padding-bottom 25%
      height 0
      overflow hidden
      position relative
      .icon-dsc
        position absolute
        left 0
        right 0
        bottom 0
        line-height .44rem
        ellipsis()
      .icons-image
        position: absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-image-content
          display 0
          margin 0 auto
          height 100%
          color $darkTextColor
          text-align center
</style>
