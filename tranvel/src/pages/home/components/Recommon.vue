<template>
<div>
  <div class="title-recommon">重要重要</div>
  <ul class="itme-contianer">
    <li class="item" v-for="item in recommontlists" :key="item.id">
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
  data(){
    return{
      recommontlists:[
        {
          id:'0001',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title:'上海迪士尼乐园',
          desc:'那些课教案设计的把控十点半漫长历史的可能放假'
        },
        {
          id:'0002',
          imgUrl:'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title:'上海迪士尼乐园',
          desc:'那些课教案设计的把控十点半漫长历史的可能放假'
        }
      ]
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
