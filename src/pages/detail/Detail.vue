<template>
    <div>
        <detail-banner></detail-banner>
        <detail-header></detail-header>
    </div>
</template>
<script>
import detailBanner from './components/Banner.vue'
import detailHeader from './components/Header.vue'
 export default{
     name:'detail',
     components:{
       detailBanner,
       detailHeader
     }
 }
</script>
<style lang="stylus" scoped>

</style>

