<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-title">{{this.sightName}}</div>
        <div class="banner-number"><span class="banner-icon iconfont">&#xe631;</span>{{this.bannerImgs.length}}</div>
      </div>
    </div>
    <common-gallary @close="handleGallaryClose" :imgs="bannerImgs" v-show="showGallary"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default{
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position : relative
    overflow : hidden
    height: 0
    padding-bottom : 55%
    .banner-img
      width:100%
    .banner-info
      position:absolute
      left:0
      right:0
      bottom:0
      line-height :.6rem
      color:#fff
      background-image:linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
      display:flex
      .banner-title
        font-size : .32rem
        flex:1
      .banner-number
        margin-top:.14rem
        padding:0 .4rem
        line-height :.32rem
        height:.4rem
        border-radius : .2rem
        gackground:rgba(0,0,0,.8)
        font-size: .24rem
        .banner-icon
          font-size:.24rem
</style>
