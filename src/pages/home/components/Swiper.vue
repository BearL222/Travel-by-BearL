<template>
  <div class='wrapper'>
      <swiper :options="swiperOption" v-if="showSwiper">
        <!-- slides -->
        <swiper-slide v-for="item of list" :key="item.id">
          <img class="swiper-img" :src="item.imgUrl">
        </swiper-slide>
        <!-- <swiper-slide><img src="https://images.pexels.com/photos/371633/pexels-photo-371633.jpeg?auto=compress&cs=tinysrgb&h=350"/></swiper-slide>
        <swiper-slide><img src="https://images.pexels.com/photos/814499/pexels-photo-814499.jpeg?auto=compress&cs=tinysrgb&h=350"/></swiper-slide> -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper() {
      return this.list.length
    }
  }
}

</script>

<style lang='stylus' scoped>
  .wrapper
    // 避免抖动
    overflow: hidden
    width: 100%
    height: 0 
    padding-bottom: 31.25%
    background: #A9A9A9
    .swiper-img
      width: 100%
</style>