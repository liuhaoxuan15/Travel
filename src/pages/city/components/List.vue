<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{this.$store.state.city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" @click="handleCityClick(item.name)" :key="item.id" v-for="item of hotCities">
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" :key="key" :ref="key" v-for="(item, key) of cities">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" @click="handleCityClick(innerItem.name)" :key="innerItem.id" v-for="innerItem of item">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        /* 滚动到element处 */
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow : hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    .title
      line-height : .54rem
      background: #eee
      padding-left : .2rem
      color: #666
      font-size: .26rem
    .button-list
      padding : .1rem .6rem .1rem .1rem
      overflow : hidden
      .button-wrapper
        float: left
        width: 33.33%
        .button
          text-align : center
          padding: .1rem 0
          margin: .1rem
          border: .02rem solid #ccc
          border-radius : .06rem
    .item-list
      .item
        line-height :.76rem
        padding-left: .2rem
</style>
