<template>
<div class="wrapper">
  <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide :key="item.id" v-for="item of swiperList">
        <img class="swiper-img" :src="item.imgUrl">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default{
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: 3000
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1812/a8/33a03fe1c213da02.jpg_750x200_dd491fc5.jpg'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/f7/72ce947f4dff4c02.jpg_750x200_aa583dba.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background : #ffffff
  .wrapper
    width : 100%
    height : 0
    overflow : hidden
    padding-bottom : 26.7%
    .swiper-img
      width : 100%
      height : 100%
</style>
