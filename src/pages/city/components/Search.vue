<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
    <div v-show="keyword" class="search-content" ref="search">
      <ul>
        <li class="search-item border-bottom" @click="handleCityClick(item.name)" :key="item.id" v-for="item of list">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNodata">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  computed: {
    hasNodata () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  props: {
    cities: Object
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    padding: 0 .1rem
    height: .72rem
    background: $bgColor
    .search-input
      box-sizing : border-box
      height: .62rem
      line-height: .62rem
      width: 100%
      text-align : center
      border-radius : .06rem
      color: #666666
      padding: 0 .1rem
  .search-content
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    overflow : hidden
    z-index:1
    background:#eee
    .search-item
      line-height : .62rem
      padding-left: .2rem
      background: #ffffff
      color : #666666
</style>
