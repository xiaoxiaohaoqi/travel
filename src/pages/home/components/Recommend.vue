<template>
  <div>
    <div class="title">热销和推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="itim-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-buttom">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/maxins.styl';
  .title
    margin-top: .2rem
    line-height: .4rem
    background: #eeeeee
    text-indent: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .itim-info
      flex: 1
      min-width: 0
      padding: .1rem
      .item-title
        line-height: 0.54rem
        font-size: .32rem
        ellipsis()
      .item-info
        line-height: 0.4rem
        color: #cccccc
        ellipsis()
      .item-buttom
        line-height: 0.14rem
        margin-top: 0.16rem
        background: #ff9300
        padding: 0.2rem
        border-radius: 0.06rem
        color: #fff
</style>
