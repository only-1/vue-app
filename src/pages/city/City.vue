<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hot="hotCities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>
<script>
import CityHeader from './components/Header.vue'
import CitySearch from './components/Search.vue'
import CityList from './components/List.vue'
import CityAlphabet from './components/Alphabet.vue'
import axios from 'axios'
export default {
  name:'city',
  components:{
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data(){
    return{
      hotCities:[],
      cities:{}

    }
  },
  methods:{
      getCityInfo(){
        axios.get('/static/mock/city.json').then(this.handleGetCityInfoSucc)
      },
      handleGetCityInfoSucc(res){
        res = res.data
        if(res.ret&&res.data){
          this.hotCities=res.data.hotCities
          this.cities=res.data.cities
        }
      }
  },
  mounted(){
      this.getCityInfo()
  }
}
</script>
<style lang="stylus" scoped>

</style>
