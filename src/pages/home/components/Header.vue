<template>
    <div class="header">
        <div class="header-left"><span class="iconfont">&#xe624</span></div>
        <div class="header-input" placeholder="请输入城市景点"><span class="iconfont">&#xe632</span>请输入城市景点</div>
        <router-link to="/city">
          <div class="header-right">{{this.$store.state.city}}<span class="iconfont">&#xe64a</span></div>
        </router-link>
    </div>
</template>
<script>
    export default{
        name:'HomeHeader'
    }
</script>
<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header
       height:$headerHeight
       display:flex
       background:$bgColor
       line-height:$headerHeight
       color:#fff
       .header-left
         width:.64rem
         text-align:center
         float:left
       .header-right
         width:1.24rem
         float:right
         color:#fff
         text-align:center
       .header-input
         flex:1
         background:#fff
         border-radius:.1rem
         margin-top:.12rem
         height:.64rem
         line-height:.64rem
         margin-left:.2rem
         color:#ccc
</style>
