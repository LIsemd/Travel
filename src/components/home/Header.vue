<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="City">
    <div class="header-right">
      {{this.city}}
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }

}
</script>

<style lang="stylus" scoped>
  @import "../../assets/styles/varibles.styl"
  @import "../../assets/styles/mixins.styl"
  .header
    display: flex
    background $bgColor
    line-height $headerHeight
    color #fff
    .header-left
      width .64rem
      float left
      .back-icon
          text-align center
          font-size .32rem
    .header-input
      flex 1
      height .64rem
      line-height .64rem
      border-radius .05rem
      background #fff
      color #ccc
      margin-top .16rem
      margin-bottom .16rem
      margin-left .2rem
      padding-left .2rem
    .header-right
      color #fff
      min-width 1.04rem
      padding 0 .1rem
      float right
      text-align center
      margin-top .05rem
      .arrow-icon
        margin-left -.04rem
        font-size 0.24rem
</style>
