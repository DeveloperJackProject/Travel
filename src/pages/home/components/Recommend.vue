<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img :src="item.imageURL" class="item-img"/>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-desc">{{item.feature}}</div>
          <div class="item-button">查看详情</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_200x200_4ab5da75.jpg',
          id: '0000',
          title: '大连圣亚海洋世界',
          feature: '浪漫大连首站，浪漫的海洋主题乐园',
          price: '25'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1707/57/5729585581b6732fa3.water.jpg_200x200_85298361.jpg',
          id: '0001',
          title: '大连森林动物园',
          feature: '',
          price: '58'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1602/39/39f6b1003abe1b2790.img.jpg_200x200_a7051b04.jpg',
          id: '0002',
          title: '老虎滩海洋公园',
          feature: '浓缩极地世界，展现海洋奇观',
          price: '50'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/201301/07/f490e9cfe240b37f93835fbb.png_200x200_7a9cff26.png',
          id: '0003',
          title: '闯关东影视城',
          feature: '',
          price: '148'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1703/94/944fc059260bd728a3.water.jpg_200x200_742cb84f.jpg',
          id: '0004',
          title: '海昌发现王国',
          feature: '',
          price: '60'
        },
        {
          imageURL: 'http://img1.qunarzz.com/wugc/p110/201204/20/a5dc43dd3cc1ae6493835fbb.jpg_200x200_8fb34099.jpg',
          id: '0005',
          title: '冰峪沟',
          feature: '具备完善住、游、餐、娱、购的综合风景区',
          price: '167'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/201311/27/086ed67b37efc84ba172143044fb4e3c.jpg_200x200_05ca3bfe.jpg',
          id: '0006',
          title: '大连东泉温泉',
          feature: '',
          price: '110'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/201305/08/5d1257030312006ac8d65eac.jpg_200x200_45d17718.jpg',
          id: '0007',
          title: '金石滩旅游度假区',
          feature: '这里最近很火哦，好多人都在点评它呢！',
          price: '49'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1509/d4/e31eb1014435ca09e5f7d7d4a3feac58.water.jpg_200x200_b5242f8f.jpg',
          id: '0008',
          title: '大连香洲旅游度假区',
          feature: '',
          price: '56'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1804/fc/fca46e521d45ddf0a3.water.jpg_200x200_7f6efd98.jpg',
          id: '0009',
          title: '星海公园',
          feature: '800多米弓形海水浴场，海天相连心旷神怡',
          price: '29'
        },
        {
          imageURL: 'http://img1.qunarzz.com/sight/p0/1706/f6/f6984dcf4034004aa3.water.jpg_200x200_8c2e70ca.jpg',
          id: '0010',
          title: '小平岛景区',
          feature: '信息产业带的龙头地段',
          price: '65'
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
