<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
         <home-Icon></home-Icon>
        <home-recommend></home-recommend>
    </div>
</template>
<script>
    import HomeHeader from './components/Header.vue'
    import HomeSwiper from './components/Swiper.vue'
    import HomeIcon from './components/Icon.vue'
    import HomeRecommend from './components/Recommend.vue'
export default{
    name:'home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcon,
        HomeRecommend
    }
}
</script>
<style lang = stylus>

</style>
