<template>
  <div>
      <div class="title">周末去哪儿</div>
      <ul>
          <li class="item border-wapper" :key="item.id" v-for="item of recommendList">
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
  data () {
    return {
      recommendList: [{
        id: '01',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg'
      }, {
        id: '02',
        title: '顺景温泉',
        desc: '773条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg'
      }, {
        id: '03',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg'
      }, {
        id: '04',
        title: '顺景温泉',
        desc: '773条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg'
      }, {
        id: '05',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg'
      }]
    }
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
    padding : 33.9%
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
