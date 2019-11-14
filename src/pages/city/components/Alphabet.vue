<template>
  <ul class="list">
    <li class="item" v-for="(item,key) in cities" :key="key">{{key}}</li>
  </ul>
</template>
<script>
export default {
  name:'Alphabet',
  props:{
    cities:Object
  }  
}
</script>
<style lang="stylus" scoped>
.list
   position:absolute
   top:1.58rem
   right:0
   bottom:0
   width:.5rem
   display:flex
   flex-direction:column
   justify-content:center
   .item
      line-height:.44rem
      text-align:center
      color:#00bcd4



</style>
