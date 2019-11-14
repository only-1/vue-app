<template>
  <div class="search">
    <input type="text"
    placeholder="输入城市名或拼音"
    class="city-search">
  </div>
</template>
<script>
export default {
  name:'search'
}
</script>
<style lang="stylus" scoped>
.search
  height 0.72rem
  padding:0 .1rem
  background:#00bcd4
  .city-search
    height 0.62rem
    line-height .62rem
    text-align:center
    width: 100%;
    border-radius:.06rem
    color:#666

</style>
