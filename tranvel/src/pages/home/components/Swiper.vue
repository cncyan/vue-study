<template>
    <div class="wrapper">
    <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item in swiperList" :key="item.id">
            <img class="swiper-img" :src="item.imgUrl" />
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
    </div>
</template>

<script>
export default {
    name:'HomeSwiper',
    data (){
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                loop:true
            },
            swiperList:[
                {
                    id:'0001',
                    imgUrl:'http://img1.qunarzz.com/piao/fusion/1807/fa/800bd7f554abf302.jpg_750x200_9d809aad.jpg'
                },
                {
                    id:'0002',
                    imgUrl:'http://img1.qunarzz.com/piao/fusion/1806/3c/c72a1ccd4d7b2202.jpg_750x200_b88bbab4.jpg'
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
    .wrapper >>> .swiper-pagination-bullet-active
      background:#ffffff
    .wrapper
      overflow:hidden
      width:100%
      height:0
      padding-bottom:26.6%
      background:#eee
      .swiper-img
        width:100%
</style>
