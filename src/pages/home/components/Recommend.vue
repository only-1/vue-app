<template>
<div>
    <div class="recommend-title">热销推荐</div>
    <ul>

           <router-link :to="'/detail/'+ item.id" tag="li" v-for="item in recom"
           :key="item.id" class="item border-bottom">
               <img :src="item.imgUrl" class="item-img">
               <div class="item-info">
                   <p class="item-title">{{item.title}}</p>
                   <p class="item-desc">{{item.desc}}</p>
                   <button class="item-button">查看详情</button>
               </div>

        </router-link>
    </ul>
</div>


</template>
<script>
export default{
    name:'recommend',
    props:{
        recom:Array
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
.item
   height:1.9rem
   display:flex
   overflow:hidden
   .item-img
      width:1.7rem
      height:1.7rem
      padding:.1rem
   .item-info
      flex:1
      min-width:0
      padding:.1rem
      .item-title
        line-height:.54rem
        font-size:.32rem
        ellipsis()
      .item-desc
        line-height:.4rem
        color:#ccc
        ellipsis()
      .item-button
        border-radius:.06rem
        background:#ff9300
        padding:0 .1rem
        color:#fff
        margin-top:.2rem


</style>
