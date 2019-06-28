<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list></city-list>
  </div>
</template>

<script>
import CityHeader from '../components/city/Header'
import CitySearch from '../components/city/Search'
import CityList from '../components/city/List'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList
  }
}
</script>

<style lang="stylus" scoped>

</style>
