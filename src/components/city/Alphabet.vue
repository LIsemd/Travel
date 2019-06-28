<template>
   <ul class="list">
     <li class="item" v-for="(item,key) of citiesList" :key="key">{{key}}</li>
   </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    citiesList: Object
  }
}
</script>

<style lang="stylus" scoped>
  @import "../../assets/styles/varibles.styl"
  .list
    position absolute
    display flex
    flex-direction column
    justify-content center
    top 1.58rem
    right 0
    bottom 0
    width: .4rem
    .item
      text-align center
      line-height .4rem
      color $bgColor
</style>
