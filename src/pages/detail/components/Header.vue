<template>
  <div>
      <router-link to="/" tag="div" v-show="showAbs"
      class="header-abs">
        <span class="iconfont header-icon">&#xe624</span>
      </router-link>
      <div class="header-fixed" v-show="!showAbs"
        :style="opacityStyle">
        <router-link to="/">
          <div class="header-left"><span class="iconfont">&#xe624</span></div>
        </router-link>
        景点详情
      </div>
  </div>
</template>
<script>
export default {
  name:'Detail-Header',
  data(){
    return{
      showAbs:true,
      opacityStyle:{
        opacity:0
      }
    }
  },
  methods:{
    handleScroll(){
      const top = document.documentElement.scrollTop
        if(top > 60){
          let opacity = top/140
          opacity = opacity > 1 ? 1 : opacity
          this.opacityStyle = {opacity}
          this.showAbs = false
        }else{
            this.showAbs = true
        }
    }
  },
  activated(){
    window.addEventListener('scroll',this.handleScroll)
  },
  deactivated(){
    window.removeEventListener('scroll',this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header-abs
  position:absolute
  left:0.2rem
  top:0.2rem
  width:.8rem
  line-height:.8rem
  text-align:center
  height:0.8rem
  border-radius:0.4rem
  background:rgba(0,0,0,.3)
  .header-icon
    color:#fff
.header-fixed
  position:fixed
  top:0
  left:0
  right:0
  height:$headerHeight
  line-height:$headerHeight
  text-align:center
  color:#fff
  background:$bgColor
  font-size:.32rem
  .header-left
    float:left
    color:#fff
</style>
