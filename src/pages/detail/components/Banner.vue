<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1608/5c/5c30160572493ba9a3.water.jpg_600x330_e1701928.jpg" alt="">
      <div class="banner-info">
        <div class="banner-title">北京乐多港奇幻乐园</div>
        <div class="banner-number"><span class="banner-icon iconfont">&#xe631;</span>39</div>
      </div>
    </div>
    <common-gallary @close="handleGallaryClose" :imgs="imgs" v-show="showGallary"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default{
  name: 'DetailBanner',
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1608/50/50712290392caab8a3.water.jpg_r_800x800_a9307d14.jpg',
        'http://img1.qunarzz.com/sight/p0/1608/76/76ca923c13ea3836a3.water.jpg_r_800x800_11fc704d.jpg']
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
