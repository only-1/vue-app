<template>
    <div class="container" @click="handerG">
      <div class="wrapper">
          <swiper :options="swiperOptions">
      <!-- slides -->
              <swiper-slide>
                <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg"/>
              </swiper-slide>
              <swiper-slide>
                <img class="swiper-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg"/>
              </swiper-slide>
              <!-- Optional controls -->
              <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name:'gallary',
  props:{
    imgs:{
      type:Array,
      default(){
        return []
      }
    }
  },
  data(){
    return{
    swiperOptions:{
      pagination:'.swiper-pagination',
      paginationType:'fraction',
      observeParents:true,
      observer:true

    }
  }
},
methods:{
  handerG(){
    this.$emit('close')
  }
}
}
</script>
<style lang="stylus" scoped>
.container
  display:flex
  flex-direction:column
  justify-content:center
  position:fixed
  left:0
  right:0
  top:0
  bottom:0
  background:#000
  z-index:99
  .wrapper
    background:#fff
    width:100%
    height:0
    padding-bottom:54%
    overflow:hidden
    .swiper-img
      width:100%
</style>
