<template>
    <div class="container" @click="handerG">
      <div class="wrapper">
          <swiper :options="swiperOptions">
      <!-- slides -->
              <swiper-slide v-for="(item,index) in imgs" :key="index">
                <img class="swiper-img" :src="item" />
              </swiper-slide>
              <!-- Optional controls -->
              <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
  </div>
</template>
<script>
export default {
  name:'Gallary',
  props:{
    imgs:{
      type:Array
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
