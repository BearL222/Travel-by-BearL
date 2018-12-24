<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
  </div>
</template>

<script>
// 局部组件
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import axios from 'axios'
import {mapState} from 'vuex'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  },
  data() {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      lastCity: ''
    }
  },
  computed: {
    ...mapState(['city'])
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo() {
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res) {
      res = res.data
      if(res.ret && res.data) {
        this.city = res.data.city
        this.swiperList = res.data.swiperList
        this.iconList = res.data.iconList
      }
      console.log(res)
    }
  },
  activated() {
    if(this.lastCity !== this.city) {
      this.lastCity = last.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>
</style>
