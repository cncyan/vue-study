<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市/景点/游玩主题</div>
    <router-link to="city"> <div class="header-right">{{this.$store.state.city}}<span class="iconfont arrow-icon">&#58954;</span></div></router-link>
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
    line-height:$headerHeight
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
      color:#ffffff
      .arrow-icon
        font-size:.24rem
</style>
