<template>
<div class="icons">
  <swiper>
    <swiper-slide v-for="(page,index) in pages" :key="index">
      <div class="icon" v-for="item in page" :key="item.id">
        <div class="icon-img">
          <img class="icon-img-content" :src="item.iconImg" />
        </div>
        <div class="icon-desc">{{item.iconDesc}}</div>
      </div>
    </swiper-slide>
  </swiper>
</div>
</template>

<script>
export default {
  name: "Icons",
  data(){
      return {
        iconsList:[
          {
            id:'0001',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0002',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0003',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0004',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0005',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0006',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0007',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0008',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0009',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          },
          {
            id:'0010',
            iconImg:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
            iconDesc:'热门景点'
          }
        ]
      }
  },
  computed:{
    pages () {
      const pages=[]
      this.iconsList.forEach((item,index) => {
        const page=Math.floor(index/8)
        if(!pages[page]){
          pages[page]=[]
      }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height:0
    padding-bottom: 50%
  .icon
    position :relative
    overflow :hidden
    width :25%
    float :left
    padding-bottom :25%
    .icon-img
      position :absolute
      top:0
      left:0
      right:0
      bottom:.2rem
      box-sizing :border-box
      padding:.1rem
      .icon-img-content
        display :block
        height :100%
        margin:0 auto
    .icon-desc
      position :absolute
      left:0
      right:0
      bottom:0
      height :.44rem
      line-height :.44rem
      text-align :center
      color:$grayText
      ellinps()

</style>
