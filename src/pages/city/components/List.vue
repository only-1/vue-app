<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
             <div class="button-wrapper">
              <div class="button">{{this.$store.state.city}}</div>
            </div>
        </div>
      </div>
      <div class="area">
       <div class="title  border-topbottom">热门城市</div>
       <div class="button-list">
           <div class="button-wrapper" v-for="item in hot" :key="item.id" @click="handleCityClick(item.name)">
             <div class="button">{{item.name}}</div>
           </div>
       </div>
    </div>
      <div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
        <div class="title  border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item" v-for="innerItem of item"
           :key="innerItem.id" @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
        </div>
      </div>
     </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name:'City-list',
  props:{
    hot:Array,
    cities:Object,
    letter:String
  },
  methods:{
      handleCityClick(city){
          this.$store.dispatch('changeCity',city)
      }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch:{
    letter(){
      if(this.letter){
       
       const element = this.$refs[this.letter][0]
       this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
.border-topbottom
   &:before
     border-color:#ccc
   &:after
     border-color:#ccc
.list
  position:absolute
  top:2rem
  left:0
  bottom:0
  right:0
  overflow: hidden
  .title
    height 0.44rem
    line-height 0.44rem
    padding-left:.2rem
    background:#eee
    color:#666
    font-size:.26rem
  .button-list
    padding: 0.1rem 0.6rem .1rem .1rem
    overflow hidden
    .button-wrapper
      width:33.33%
      float:left
      .button
        margin:.1rem
        text-align:center
        border:.02rem solid #ccc
        padding:.1rem 0
        border-radius:0.6rem
  .item-list
    .item
      line-height:.76rem
      color:#666
      padding-left:.2rem
      border-bottom:.01rem solid #ccc

</style>
