<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommandList" :key="item.id">
          <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommand',
  data () {
    return {
      recommandList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1506/f6/f6b727f036fe5d6d.water.jpg_200x200_a3c26b4d.jpg',
        title: '鼓浪屿',
        desc: '你离鼓浪屿只有一张船票的距离~'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1506/f6/f6b727f036fe5d6d.water.jpg_200x200_a3c26b4d.jpg',
        title: '鼓浪屿',
        desc: '你离鼓浪屿只有一张船票的距离~'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1506/f6/f6b727f036fe5d6d.water.jpg_200x200_a3c26b4d.jpg',
        title: '鼓浪屿',
        desc: '你离鼓浪屿只有一张船票的距离~'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "../../assets/styles/mixins.styl"
  .title
    line-height .8rem
    background-color: #eee
    text-indent .2rem
    margin-top .1rem
  .item
    overflow hidden
    display flex
    height 1.9rem
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
        color #ccc
        ellipsis()
      .item-button
        background-color: #ff9300
        line-height .44rem
        padding 0 .1rem
        border-radius .06rem
        margin-top .25rem
        color #fff
</style>
