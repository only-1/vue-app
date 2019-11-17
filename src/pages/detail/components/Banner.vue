<template>
<div>
    <div class="banner" @click="handleBanner">
      <img class="banner-img"
      :src=bannerImg>
       <div class="banner-info">
         <div class="banner-title">{{this.sightName}}</div>
         <div class="banner-number">{{this.bannerImg.length}}</div>
       </div>
    </div>
     <fade-animation>
        <common-Gallary :imgs = "gallaryImgs" @close="handlecommon"
        v-show="showGallary"></common-Gallary>
  </fade-animation>
  </div>
</template>
<script>
import commonGallary from '@/common/gallary/Gallary'
import FadeAnimation from '@/common/fade/Fade'
export default {
  name:'DetailBanner',
  props:{
    bannerImg:String,
    gallaryImgs:Array,
    sightName:String
  },
  data(){
    return{
      showGallary:false

    }
  },
  components:{
    commonGallary,
    FadeAnimation
  },
  methods:{
    handleBanner(){
      this.showGallary = true
    },
    handlecommon(){
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
.banner
  position relative
  overflow:hidden
  height:0
  padding-bottom:55%
  .banner-img
    width:100%
  .banner-info
    display:flex
    position:absolute
    left:0
    right:0
    bottom:0
    line-height:.6rem
    color:#fff
    background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
    .banner-title
      flex:1
      font-size:.32rem
      padding:0 .2rem
    .banner-number
      padding:0 .4rem
      height 0.4rem
      line-height:.4rem
      border-radius 0.2rem
      margin-top:.07rem
      background:rgba(0,0,0,.8)
</style>
