<template>
    <div class="header">
        <div class="header-left">
          <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-input">
          <span class="iconfont">&#xe632;</span>
          输入城市/景点/游玩/主题
        </div>
        <div class="header-right">
          城市
          <span class="iconfont city">&#xe600;</span>
          </div>
    </div>
</template>

<script>
export default{
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  .header
    display : flex
    line-height: .86rem
    background: #00bcd4
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
      margin-left : .2rem
</style>
