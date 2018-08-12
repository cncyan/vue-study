<template>
<div>
  <home-header></home-header>
  <home-swiper :list="swiperList"></home-swiper>
  <home-icon :list="iconsList"></home-icon>
  <home-recommon :list="recommonList"></home-recommon>
  <home-weekend :list="weekendList"></home-weekend>
</div>
</template>

<script>
import HomeHeader from './components/HomeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcon from './components/Icons'
import HomeRecommon from './components/Recommon'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommon,
    HomeWeekend
  },
  data(){
    return{
      swiperList:[],
      iconsList:[],
      recommonList:[],
      weekendList:[]
    }
  },
  methods:{
    getHomeInfo(){
      var self=this;
      axios.get('/static/mock/index.json').then(this.getContent)
    },
    getContent(res){
      if(res.data.ret){
        this.swiperList=res.data.data.swiperList;
        this.iconsList=res.data.data.iconList;
        this.recommonList=res.data.data.recommendList;
        this.weekendList=res.data.data.weekendList;
      }
    }
  },
  mounted(){
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
