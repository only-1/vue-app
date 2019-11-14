<template>
<div>
  <div class="search">
    <input type="text" placeholder="输入城市名或拼音" class="city-search" 
    v-model="keyword">
  </div>
  <div class="search-content" ref="sear" v-show="keyword">
    <ul >
      <li v-for="item in list" class="search-item" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
     <li  class="search-item" v-show="!list.length">没有找到匹配数据</li> 
    </ul> 
  </div>
</div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name:'search',
  props:{
    cities:Object
  },
  data(){
    return{
      keyword:'',
      list:[],
      timer:null
    }
  },
  watch:{
    keyword(){
        if(this.timer){
          clearTimeout(this.timer)
        }
        if(!this.keyword){
          this.list = []
          return
        }
        this.timer = setTimeout(()=>{
          const result=[]
          for(let i in this.cities){
            this.cities[i].forEach((value)=>{
             if(value.spell.indexOf(this.keywork)>-1||value.name.indexOf(this.keywork)>-1){
                result.push(value)
             }
            })
          }
         this.list=result
        },100)
    }
  },
  mounted(){
    this.scroll = new BScroll(this.$refs.sear)
  },
  methods:{
      handleCityClick(city){
           this.$store.dispatch('changeCity',city)
           this.$router.push('/')
      }
  }
}
</script>
<style lang="stylus" scoped>
.search
  height 0.72rem
  padding:0 .1rem
  background:#00bcd4
  .city-search
    height 0.62rem
    line-height .62rem
    text-align:center
    width: 100%;
    border-radius:.06rem
    color:#666
.search-content
  position:absolute
  top:1.58rem
  left:0
  right:0
  bottom:0
  overflow:hidden
  background:#eee
  z-index:1
  .search-item
    color:#666
    line-height:.62rem
    padding-left:.2rem
    background:#fff
    border:.01rem solid #ccc

</style>
