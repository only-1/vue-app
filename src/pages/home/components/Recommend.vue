<template>
<div>
    <div class="recommend-title">热销推荐</div>
    <ul>
        <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
            <img :src="item.imgUrl" class="item-img">
            <div class="item-info">
                <p class="item-title">{{item.title}}</p> 
                <p class="item-desc">{{item.desc}}</p>
                <button class="item-button">查看详情</button>
            </div>   
        </li>
    
    </ul>
</div>


</template>
<script>
export default{
    name:'recommend',
    data(){
        return{
            recommendList:[
                {
                    id:'001',
                    title:'大连圣木管',
                    desc:'快来看快来看啊啊啊啊啊',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/033f6526-1db0-40c7-93c4-ba3572c04b4f.jpg_r_480x320x90_df159252.jpg'
                },
                {
                    id:'002',
                    title:'日本',
                    desc:'我想去哈哈',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/033f6526-1db0-40c7-93c4-ba3572c04b4f.jpg_r_480x320x90_df159252.jpg'
                },
                {
                    id:'003',
                    title:'法国',
                    desc:'我想去哈哈',
                    imgUrl:'//imgs.qunarzz.com/vs_ceph_vs_tts/033f6526-1db0-40c7-93c4-ba3572c04b4f.jpg_r_480x320x90_df159252.jpg'
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