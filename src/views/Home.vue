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

export default {
  name: 'Home',
  components: {
    HomeWeekend,
    HomeRecommand,
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>
<style>
</style>
