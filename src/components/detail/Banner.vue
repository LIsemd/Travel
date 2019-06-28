<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1901/51/51bee94d1a403371a3.img.png_600x330_db71d6a0.png">
      <div class="banner-info">
        <div class="banner-title">厦门中非世野野生动物园</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63e;</span>
          39
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from '../../common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      imgs: ['http://img1.qunarzz.com/sight/p0/1901/5d/5d3287abe8980332a3.img.png_r_800x800_a8a896a6.png',
        'http://img1.qunarzz.com/sight/p0/1901/5d/5d3287abe8980332a3.img.png_r_800x800_a8a896a6.png'],
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      display flex
      color #fff
      background-image linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        height .32rem
        line-height .32rem
        margin-top .14rem
        padding 0 .4rem
        border-radius .2rem
        font-size .24rem
        background-color rgba(0,0,0,.8)
        .banner-icon
          font-size .24rem

</style>
