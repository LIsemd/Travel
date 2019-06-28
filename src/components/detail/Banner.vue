<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" />
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63e;</span>
          {{this.gallaryImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
        :gallaryImgs="gallaryImgs"
        v-show="showGallary"
        @close="handleGallaryClose"
      >
      </common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from '../../common/gallary/Gallary'
import FadeAnimation from '../../common/fade/Fade'

export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
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
