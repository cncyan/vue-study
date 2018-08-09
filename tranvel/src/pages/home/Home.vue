<template>
<div>
  <home-header></home-header>
  <home-swiper></home-swiper>
  <home-icon></home-icon>
  <home-recommon></home-recommon>
</div>
</template>

<script>
import HomeHeader from './components/HomeHeader'
import HomeSwiper from './components/Swiper'
import HomeIcon from './components/Icons'
import HomeRecommon from './components/Recommon'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcon,
    HomeRecommon
  },
  methods:{
    getHomeInfo(){
      axios.get('/static/mock/index.json').then(function(res){
        console.log(res.data)
      })
    }
  },
  mounted(){
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
