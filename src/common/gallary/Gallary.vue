<template>
    <div class="container" @click="handleGallaryClick">
      <div class="wrapper">
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, index) in imgs" :key="index">
            <img class="gallary-img" :src="item"/>
          </swiper-slide>
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return ['http://img1.qunarzz.com/sight/p0/1901/5d/5d3287abe8980332a3.img.png_r_800x800_a8a896a6.png',
          'http://img1.qunarzz.com/sight/p0/1901/5d/5d3287abe8980332a3.img.png_r_800x800_a8a896a6.png']
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
  .container
    display flex
    flex-direction column
    justify-content center
    z-index 99
    position fixed
    left 0
    right 0
    top 0
    bottom 0
    background-color #000
    .wrapper
      width 100%
      margin-top 50%
      height 0
      padding-bottom 100%
      .gallary-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -1rem
</style>
