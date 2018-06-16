<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img :src="item.imageURL" class="item-img"/>
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.desc}}</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          imageURL: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          id: '0000',
          title: '北京必游TOP10',
          desc: '来北京必去的景点非这些地方莫属'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          id: '0001',
          title: '寻找北京的皇城范儿',
          desc: '数百年的宫廷庙宇，至今依旧威严霸气'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
          id: '0002',
          title: '学生最爱的博物馆',
          desc: '周末干嘛？北京很多博物馆已经免费开放啦'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/source/1505/b2/fde1bfcd057a52.jpg_r_640x214_bbf3fa44.jpg',
          id: '0003',
          title: '儿童剧场，孩子的乐园',
          desc: '带宝贝观看演出，近距离体验艺术的无穷魅力'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/source/1507/18/2d554e22faa25f.jpg_r_640x214_2a966a54.jpg',
          id: '0004',
          title: '爱上庄园',
          desc: '庄园让臭美的你秒变白富美，高富帅'
        }
      ]
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
  .item-img-wrapper
    overflow hidden
    height 0
    padding-bottom 33.9%
    .item-img
      width 100%
  .item-info
    padding .1rem
    text-align left
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      height .4rem
      color #eee
      ellipsis()
</style>
