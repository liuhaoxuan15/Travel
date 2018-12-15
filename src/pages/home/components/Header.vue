<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-input">
          <span class="iconfont">&#xe632;</span>
          输入城市/景点/游玩/主题
        </div>
        <router-link to="/city">
          <div class="header-right">
            {{this.city}}
            <span class="iconfont city">&#xe600;</span>
          </div>
        </router-link>
    </div>
</template>

<script>
export default{
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header
    display : flex
    line-height: $headerHeight
    background: $bgColor
    color: #ffffff
    .header-left
      width: .64rem
      float: left
      text-align :center
    .header-input
      flex: 1
      padding-left : .2rem
      width: 5rem
      margin-top: .12rem
      line-height: .64rem
      height: .64rem
      margin-left: .2rem
      background: #ffffff
      border-radius: .1rem
      color: #cccccc
    .header-right
      width: 1.24rem
      float: right
      text-align : center
      color : white
      .city
        font-size : .2rem
</style>
