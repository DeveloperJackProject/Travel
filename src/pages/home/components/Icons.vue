<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icons-image">
            <img class="icon-image-content" :src="item.imageUrl">
          </div>
          <p class="icon-dsc">{{item.text}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        loop: true
      },
      iconList: [
        {
          id: '0001',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          text: '门票景点'
        }, {
          id: '0002',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          text: '一日游'
        }, {
          id: '0003',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/f5/a963333e1fa802.png',
          text: '本地玩乐'
        }, {
          id: '0004',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          text: '动植物园'
        }, {
          id: '0005',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          text: '必游榜单'
        }, {
          id: '0006',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
          text: '自然风光'
        }, {
          id: '0007',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/27/dac2bcf9added702.png',
          text: '海滨海岛'
        }, {
          id: '0008',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
          text: '踏青赏花'
        }, {
          id: '0009',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
          text: '城市观光'
        }, {
          id: '0010',
          imageUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          text: '全部玩乐'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
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
