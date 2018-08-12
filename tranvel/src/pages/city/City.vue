<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hot="hotcities" :letter="letter"></city-list>
    <city-Alphabet :cities="cities" @change="giveletter"></city-Alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
export default {
  name: 'City',
  components:{
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data(){
    return {
      cities:{},
      hotcities:[],
      letter:''
    }
  },
  methods:{
    getdata(){
       axios.get('/static/mock/city.json').then(this.getcitydata)
    },
    getcitydata(res){
      if(res.data.ret){
        this.cities=res.data.data.cities
        this.hotcities=res.data.data.hotCities
      }
    },
    giveletter(letter){
      this.letter=letter;
    }
  },
  mounted(){
    this.getdata()
  }
}
</script>

<style lang="stylus" scoped>

</style>
