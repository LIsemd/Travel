<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommand></home-recommand>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
import HomeIcons from '../components/home/Icons'
import HomeRecommand from '../components/home/Recommand'
import HomeWeekend from '../components/home/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeWeekend,
    HomeRecommand,
    HomeHeader,
    HomeSwiper,
    HomeIcons
  },
  methods: {
    getHomeInfo () {
      axios.get('/mock/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      console.log(res)
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>
<style>
</style>
