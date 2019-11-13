<template>
<div>
    <div class="recommend-title">周末去哪</div>
    <ul>
        <li class="item border-bottom" v-for="item in weed" :key="item.id">
            <div class="item-img-wrapper">
                <img :src="item.imgUrl" class="item-img">
            </div>
            <div class="item-info">
                <p class="item-title">{{item.title}}</p> 
                <p class="item-desc">{{item.desc}}</p>
               
            </div>   
        </li>
    
    </ul>
</div>


</template>
<script>
export default{
    name:'weekend',
    props:{
        weed:Array
    },
    data(){
        return{

        }
    }
}


</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.recommend-title
   margin-top:.2rem
   line-height:.4rem
   background:#eee
   text-indent:.2rem
   .item-img-wrapper
     height:0
     overflow:hidden
     padding-bottom:33.3%
     .item-img
        width:100%
        padding:.1rem
.item-info
   padding:.1rem
   .item-title
     line-height:.54rem
     font-size:.32rem
     ellipsis()
   .item-desc
     line-height:.4rem
     color:#ccc
     ellipsis()
</style>