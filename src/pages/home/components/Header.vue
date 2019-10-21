<template>
  <div class="header">
    <div class="header-left">
      <i class="iconfont iconmjiantou-copy"></i>
    </div>
    <div class="header-input">
      <i class="iconfont iconiconfontshouyezhuyetubiao05"></i>
      输入城市经典游玩物体
    </div>
    <div class="header-right">
      {{this.city}}
      <i class="iconfont iconarrow"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header
    height: .86rem
    display: flex
    background: $bgColor
    color #ffffff
    .header-left
      width: .64rem
      line-height .86rem
      float: left
      text-align center
      i
        font-size 20px
    .header-input
      flex: 1
      background #ffffff
      height .64rem
      line-height .64rem
      margin-top .1rem
      margin-left .64rem
      border-radius .1rem
      color #000
      padding-left .2rem
    .header-right
      width:1.24rem
      line-height .86rem
      float: right
      text-align center
      i
        font-size .2rem
</style>
