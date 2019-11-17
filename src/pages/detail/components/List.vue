<template>
  <div>
      <div class="item" v-for="(item,index) in list"
      :key="index">
        <div class="item-title">
          <span class="iconfont  icon-list">&#xe64a</span>
          <span class="item-icon">{{item.title}}</span>
        </div>
        <div v-if="item.children" class="item-children">
          <detail-list :list="item.children"></detail-list>
        </div>
      </div>
  </div>
</template>
<script>
export default {
  name:'detail-list',
  props:{
          list:Array
        }
}
</script>
<style lang="stylus" scoped>
.item-title
  line-height:.8rem
  font-size:.32rem
  border-bottom:1px solid #ccc
  padding:0 .2rem
  .icon-list
    color:#00bcd4
.item-children
  padding-left:.4rem
</style>
