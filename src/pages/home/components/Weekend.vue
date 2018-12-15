<template>
  <div>
      <div class="title">周末去哪儿</div>
      <ul>
          <li class="item border-wapper" :key="item.id" v-for="item of list">
            <div class="item-img-weekend">
              <img class="item-img" :src="item.imgUrl" alt="">
            </div>
            <div class="item-info">
              <p class="item-title">{{item.title}}</p>
              <p class="item-desc">{{item.desc}}</p>
            </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height : .8rem
    background : #eeeeee
    text-indent : .2rem
  .item-img-wapper
    height: 0
    overflow : hidden
    padding : 37.09%
  .item-img
    width : 100%
  .item-info
    padding: .1rem
    .item-title
      line-height : .54rem
      font-size : .32rem
      ellipsis()
    .item-desc
      line-height : .4rem
      color: #cccccc
      ellipsis()

</style>
