<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :list="swiperList"></home-swiper>
         <home-Icon :list="iconList"></home-Icon>
        <home-recommend :recom="recommendList"></home-recommend>
         <home-weekend :weed="weekendList"></home-weekend>
    </div>
</template>
<script>
    import HomeHeader from './components/Header.vue'
    import HomeSwiper from './components/Swiper.vue'
    import HomeIcon from './components/Icon.vue'
    import HomeRecommend from './components/Recommend.vue'
    import HomeWeekend from './components/Weekend.vue'
    import axios from 'axios'
export default{
    name:'home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcon,
        HomeRecommend,
        HomeWeekend
    },
    data(){
       return{
           city:'',
           swiperList:[],
           iconList:[],
           recommendList:[],
           weekendList:[]
       }
    },
    methods:{
        getHomeInfo(){
            axios.get('/static/mock/index.json').then(this.getHomeInfoSucc)
        },
       getHomeInfoSucc(res) {
           console.log(res)
           res = res.data
           console.log(res)
           if(res.ret&&res.data){
               this.city = res.data.city
               this.swiperList = res.data.swiperList
               this.iconList = res.data.iconList
                this. recommendList = res.data. recommendList
                 this. weekendList = res.data. weekendList
           }
       }
    },
    mounted(){
        this.getHomeInfo()
    }

}
</script>
<style lang = stylus>

</style>
