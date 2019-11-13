<template>
    <div class="icons">
        <swiper>
            <swiper-slide v-for="(page,index) in pages" :key="index">
                <div class="icon"  v-for="(item) in page" :key="item.id">
                    <div class="icon-img">
                        <img :src='item.imgUrl' class="con-img-content">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default{
    name:'icon',
    data(){
        return{
            iconList:[
                {id:'0001',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                },
                 {id:'0002',
                imgUrl:'https://s.qunarzz.com/m_bus_search/images/icon_11.png',
                desc:'订单我的'
                },
                {id:'0003',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                },
                {id:'0004',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }
                ,
                {id:'0005',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }
                ,
                {id:'0006',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }
                ,
                {id:'0007',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }
                ,
                {id:'0008',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }
                ,
                {id:'0009',
                imgUrl:'http://s.qunarzz.com/busapp/bus/icon_open_flow_scene.png',
                desc:'景点门票'
                }     
            ]
        }
    },
    computed:{
        pages(){
            const pages = []
            this.iconList.forEach((item,index)=>{
                const page = Math.floor(index/8)
                console.log(page)
                if(!pages[page]){
                    pages[page]=[]
                }
                pages[page].push(item)   
            })
           return pages;
        }
    }
}
</script>
<style  lang="stylus" scoped>
    @import '~styles/mixins.styl'
    .icons>>>.swiper-container
      height:0
      padding-bottom:50%
    .icon
       position:relative
       width:25%
       height:0
       float:left
       padding-bottom:25%
       .icon-img
         position:absolute
         top:0;
         left:0;
         right:0;
         bottom:.44rem
         box-sizing:border-box
         padding:.1rem
         .con-img-content
            display:block
            margin:0 auto
        .icon-desc
           position:absolute
           left:0;
           right:0;
           bottom:0
           line-height:.44rem
           color:#333
           box-sizing:border-box
           padding:.1rem 
           text-align: center;
           ellipsis()
</style>