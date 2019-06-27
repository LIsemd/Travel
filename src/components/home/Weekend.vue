<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommandList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
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
      recommandList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/8f/bf3a40e4afcf29.jpg_r_640x214_90225212.jpg',
        title: '泉心泉意',
        desc: '这个冬天不干燥，养生养颜休闲一举两得，这里有厦门独特的温泉渡假旅游区'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/8f/bf3a40e4afcf29.jpg_r_640x214_90225212.jpg',
        title: '泉心泉意',
        desc: '这个冬天不干燥，养生养颜休闲一举两得，这里有厦门独特的温泉渡假旅游区'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/8f/bf3a40e4afcf29.jpg_r_640x214_90225212.jpg',
        title: '泉心泉意',
        desc: '这个冬天不干燥，养生养颜休闲一举两得，这里有厦门独特的温泉渡假旅游区'
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
  .item-img-wrapper
    overflow: hidden
    height 0
    padding-bottom 33.9%
  .item-img
    width 100%
  .item-info
    padding .1rem
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      color #ccc
      padding-right 1rem
      ellipsis()
</style>
