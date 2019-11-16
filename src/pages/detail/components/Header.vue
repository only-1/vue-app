<template>
<div>
    <div class="banner" @click="handleBanner">
      <img class="banner-img"
      src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg" alt="">
       <div class="banner-info">
         <div class="banner-title">大连圣地</div>
         <div class="banner-number">39</div>
       </div>
    </div>
  <common-Gallary :imgs="imgs" @close="handlecommon"
  v-show="showGallary"></common-Gallary>
  </div>
</template>
<script>
import commonGallary from '@/common/gallary/Gallary'
export default {
  name:'Detail-Header',
  data(){
    return{
      img:[],
      showGallary:false
    }
  },
  components:{
    commonGallary
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
