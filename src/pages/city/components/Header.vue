<template>
  <div class="header">
    <router-link to="/">
      <i class="iconfont iconmjiantou-copy header-back"></i>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header
    overflow: hidden
    line-height: $headerHeight
    height: $headerHeight
    text-align: center
    color: #fff
    background: $bgColor
    font-size: 0.32rem
    .header-back
      width: 0.64rem
      text-align: center
      font-size: .4rem
      position: absolute
      left: 0.1rem
      color: #fff
</style>
