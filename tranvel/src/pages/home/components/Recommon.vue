<template>
<div>
  <div class="title-recommon">重要重要</div>
  <ul class="itme-contianer">
    <li class="item" v-for="item in list" :key="item.id">
      <div class="itme-wraperimg">
        <img class="item-img" :src="item.imgUrl"/>
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-btn">查看更多</button>
      </div>
    </li>
  </ul>
</div>
</template>

<script>
export default {
  name: "Recommon",
  props:{
    list:Array
  },
  data(){
    return{
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .title-recommon
    line-height:.8rem
    text-indent:.2rem
    background:#eee
    margin-top:.2rem
  .itme-contianer
    width :100%
    .item
      width: 100%
      height:2.2rem
      padding :.1rem
      overflow: hidden
      .itme-wraperimg
        float :left
        overflow hidden
        width :25%
        height:0
        padding-bottom :25%
        .item-img
          display:inline-block
          width:100%
          height: auto
      .item-info
        height:auto
        float :right
        width :75%
        box-sizing:border-box
        padding-left .2rem
        .item-title
          margin-top: .26rem
          height: .44rem
          color: #212121
          font-size: .32rem
          line-height: .44rem
          ellinps()
        .item-desc
          overflow: hidden;
          margin-top: .2rem
          padding-right: .4rem;
          color: #616161;
          font-size: .24rem;
          line-height: .42rem;
          ellinps()
        .item-btn
          background :$bgColor
          color:#ffffff
          border:none
          padding:.05rem
          border-radius :.1rem
          margin-top:.2rem


</style>
