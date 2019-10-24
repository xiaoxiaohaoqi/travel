<template>
  <div class="header">
    <div class="header-left">
      <i class="iconfont iconmjiantou-copy"></i>
    </div>
    <div class="header-input">
      <i class="iconfont iconiconfont shouyezhuyetubiao05"></i>
      输入城市经典游玩物体
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.city}}
        <i class="iconfont iconarrow"></i>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
  .header
    height: $headerHeight
    display: flex
    background: $bgColor
    color #ffffff
    .header-left
      width: .64rem
      line-height $headerHeight
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
      min-width: 1.04rem
      padding 0 .1rem
      line-height .86rem
      float: right
      color: #fff
      text-align center
      i
        font-size .2rem
</style>
