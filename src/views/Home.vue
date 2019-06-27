<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommand></home-recommand>
  </div>
</template>

<script>
import HomeHeader from '../components/home/Header'
import HomeSwiper from '../components/home/Swiper'
import HomeIcons from '../components/home/Icons'
import HomeRecommand from '../components/home/Recommand'

export default {
  name: 'Home',
  components: {
    HomeRecommand,
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>
<style>
</style>
