<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-image" :src="item.imageUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          imageUrl: 'https://b2-q.mafengwo.net/s10/M00/4B/E6/wKgBZ1oKu-uAI6yuAAFxwUc4cgY85.jpeg'
        },
        {
          id: '0002',
          imageUrl: 'https://p1-q.mafengwo.net/s11/M00/39/40/wKgBEFsP1vGABq8tAAGI1yRVDos14.jpeg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color aliceblue
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 40%
    .swiper-image
      width 100%

</style>
