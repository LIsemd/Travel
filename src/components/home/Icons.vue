<template>
    <div class="icons">
      <swiper>
        <swiper-slide v-for="(page, index) of pages" :key="index">
          <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-img">
              <img class="icon-img-content" :src="item.iconUrl" :alt="item.text">
            </div>
            <p class="icon-dsc">{{item.text}}</p>
          </div>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '01',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        text: '景点门票'
      }, {
        id: '02',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        text: '一日游'
      }, {
        id: '03',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        text: '厦门必游'
      }, {
        id: '04',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/97/02f5043b51b2102.png',
        text: '鼓浪屿'
      }, {
        id: '05',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png',
        text: '武夷山'
      }, {
        id: '06',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/47/c2b659e048b11602.png',
        text: '主题乐园'
      }, {
        id: '07',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        text: '动植物园'
      }, {
        id: '08',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
        text: '展馆展览'
      }, {
        id: '09',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
        text: '游船观光'
      }, {
        id: '10',
        iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        text: '水上乐园'
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
  @import "../../assets/styles/varibles.styl"
  @import "../../assets/styles/mixins.styl"
  .icons >>> .swiper-container
    height 0
    padding-bottom 50%
  .icons
    margin-top .1rem
    .icon
      position: relative
      float left
      width 25%
      height 0
      padding-bottom 22.5%
      .icon-img
        position: absolute
        top 0
        left 0
        right 0
        bottom .44rem
        box-sizing border-box
        padding .1rem
        .icon-img-content
          height 100%
          margin 0 auto
          display: block
      .icon-dsc
        position: absolute
        bottom  0
        left 0
        right 0
        height .44rem
        line-height .44rem
        color $darkTextColor
        text-align center
        ellipsis()
</style>
