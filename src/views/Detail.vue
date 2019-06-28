<template>
  <div>
    <detail-banner :sightName="sightName"
                   :bannerImg="bannerImg"
                   :gallaryImgs="gallaryImgs">
    </detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from '../components/detail/Banner'
import DetailHeader from '../components/detail/Header'
import DetailList from '../components/detail/List'
import axios from 'axios'

export default {
  // 1.递归组件 2.取消缓存 3.开发调试
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: [],
      lastId: ''
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/mock/detail.json', {
        params: this.$route.params.id
      }).then(this.getInfoSucc)
    },
    getInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
    this.lastId = this.$route.params.id
  },
  activated () {
    if (this.lastId !== this.$route.params.id) {
      this.lastId = this.$route.params.id
      this.getDetailInfo()
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>
