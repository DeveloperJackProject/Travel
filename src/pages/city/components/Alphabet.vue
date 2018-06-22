<template>
  <ul class="list">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      @touchstart.prevent="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
      @click="handLetterleClick"
      :ref="item"
    >{{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  computed: {
    letters () {
      const letters = Object.keys(this.cities)
      return letters
    }
  },
  methods: {
    handLetterleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart (e) {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY
          const index = Math.floor((touchY - this.startY) / 20)
          this.$emit('change', this.letters[index])
        }, 16)
      }
    },
    handleTouchEnd (e) {
      this.touchStatus = false
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].getBoundingClientRect().top
    console.log(this.startY)
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .list
    display flex
    flex-direction column
    justify-content center
    position absolute
    right 0
    top 1.6 rem
    bottom 0
    width .4rem
    .item
      line-height .4rem
      text-align center
      color $bgColor
</style>
