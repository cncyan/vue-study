<template>
    <div class="wrapper">
    <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="item in list" :key="item.id">
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
    props:{
      list:Array
    },
    data (){
        return {
            swiperOption: {
                pagination:'.swiper-pagination',
                loop:true
            }
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
      padding-bottom:30%
      background:#eee
      .swiper-img
        width:100%
</style>
