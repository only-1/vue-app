<template>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
         <home-Icon></home-Icon>
    </div>
</template>
<script>
    import HomeHeader from './components/Header.vue'
    import HomeSwiper from './components/Swiper.vue'
    import HomeIcon from './components/Icon.vue'
export default{
    name:'home',
    components:{
        HomeHeader,
        HomeSwiper,
        HomeIcon 
    }
}
</script>
<style lang = stylus>

</style>
