<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-w">
          <img :src="item.imgUrl" alt="" class="item-img-wrapper">
        </div>
        <div class="itim-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
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
  .item-img-warpper
    height: 0;
    overflow: hidden
    padding-bottom: 37.09%
    .item-img
      width: 100%
  .itim-info
    padding: .1rem
    margin-bottom: 0.2rem
    .item-title
      line-height: 0.54rem
      font-size: .32rem
      ellipsis()
    .item-info
      line-height: 0.4rem
      color: #cccccc
      ellipsis()
</style>
