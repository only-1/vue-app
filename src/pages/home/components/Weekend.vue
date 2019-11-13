<template>
<div>
    <div class="recommend-title">周末去哪</div>
    <ul>
        <li class="item border-bottom" v-for="item in WeekendList" :key="item.id">
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
    data(){
        return{
            WeekendList:[
                {
                    id:'001',
                    title:'大连圣木管',
                    desc:'快来看快来看啊啊啊啊啊',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/a2ba98f7-a7dc-4b86-be43-2802a1206879.jpg_r_480x320x90_3e4dbe86.jpg'
                },
                {
                    id:'002',
                    title:'日本',
                    desc:'我想去哈哈',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/a2ba98f7-a7dc-4b86-be43-2802a1206879.jpg_r_480x320x90_3e4dbe86.jpg'
                },
                {
                    id:'003',
                    title:'法国',
                    desc:'我想去哈哈',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/a2ba98f7-a7dc-4b86-be43-2802a1206879.jpg_r_480x320x90_3e4dbe86.jpg'
                }
            ]
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