<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
    <div class="header-right">城市<span class="iconfont arrow-icon">&#58954;</span></div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
  /*1rem=html font-size 50px*/
  @import '~styles/varibles.styl'
  .header
    display:flex
    line-height:.86rem
    background:$bgColor
    color:#ffffff
    .header-left
      float:left
      width:.64rem
      .back-icon
        text-align:center
        font-size:.4rem
    .header-input
      flex:1
      height:.62rem
      line-height:.62rem
      margin-top:.12rem
      margin-left:.2rem
      padding-left:.2rem
      background:#ffffff
      border-radius:.1rem
      color:#cccccc
    .header-right
      width:1.24rem
      float:right
      text-align:center
      .arrow-icon
        font-size:.24rem
</style>
