<template>
    <div>
        <detail-banner
        :sightName="sightName"
        :gallaryImgs="gallaryImgs"
        :bannerImg="bannerImg"></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="categoryList"></detail-list>
    </div>
</template>
<script>
import detailBanner from './components/Banner.vue'
import detailHeader from './components/Header.vue'
import detailList from './components/List.vue'
import axios from 'axios'
 export default{
     name:'detail',
     components:{
       detailBanner,
       detailHeader,
       detailList
     },
     data(){
       return{
         bannerImg:'',
         categoryList:[],
          gallaryImgs:[],
          sightName:''
       }
     },
     methods:{
       getDetailInfo(){
      //    axios.get('/static/mock/detail.json?id='+this.$route.params.id+).then(this.getInfo())
      //  },
      axios.get('/static/mock/detail.json',{
        params:{
          id:this.$route.params.id
        }
      }).then(this.getInfo)
       },
       getInfo(res){
         res = res.data
         if(res.ret && res.data){
            this.bannerImg =res.data.bannerImg
            this.categoryList =res.data.categoryList
            this.gallaryImgs=res.data.gallaryImgs
            this.sightName =res.data.sightName
         }
       }
     },
     mounted(){
       this.getDetailInfo()
     }
 }
</script>
<style lang="stylus" scoped>
.content
  height:50rem
</style>

