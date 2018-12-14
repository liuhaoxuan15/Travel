<template>
  <div>
      <div class="title">热销推荐</div>
      <ul>
          <li class="item border-bottom" :key="item.id" v-for="item of recommendList">
                  <img class="item-img" :src="item.imgUrl" alt="">
              <div class="item-info">
                <p class="item-title">{{item.title}}</p>
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">查看详情</button>
              </div>
          </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '01',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg'
      }, {
        id: '02',
        title: '顺景温泉',
        desc: '773条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/fa/fa08335dde3512faa3.img.jpg_200x200_8b29ca1f.jpg'
      }, {
        id: '03',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg'
      }, {
        id: '04',
        title: '顺景温泉',
        desc: '773条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/fa/fa08335dde3512faa3.img.jpg_200x200_8b29ca1f.jpg'
      }, {
        id: '05',
        title: '故宫',
        desc: '337020条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg'
      }, {
        id: '06',
        title: '顺景温泉',
        desc: '773条评论',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1811/fa/fa08335dde3512faa3.img.jpg_200x200_8b29ca1f.jpg'
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
    margin-top : .2rem
  .item
    overflow : hidden
    display: flex
    height: 1.9rem
    .item-img
      width : 1.7rem
      height : 1.7rem
      padding: .1rem
    .item-info
      min-width: 0
      flex: 1
      padding: .1rem
      .item-title
        line-height : .54rem
        font-size : .32rem
        ellipsis()
      .item-desc
        line-height : .4rem
        color: #cccccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top : .16rem
        background: #ff9300
        padding:0 .2rem
        border-radius: .06rem
        color: #ffffff
</style>
