<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="buttom-list">
          <div class="bottom-wrapper">
            <div class="bottom">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="buttom-list">
          <div class="bottom-wrapper" v-for="item of hot" :key="item.id" @click="handleCityClick(item.name)">
            <div class="bottom">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div
            class="item border-bottom"
            v-for="innerItem of item"
            :key="innerItem.id"
            @click="handleCityClick(innerItem.name)"
          >
            {{innerItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const elment = this.$refs[this.letter][0]
        this.scroll.scrollToElement(elment)
      }
    }
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color:#ccc
    &:after
      border-color:#ccc
    .border-bottom
    &:before
      border-color:#ccc
    &:after
      border-color:#ccc
  .list
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom:0
    .title
      line-height: .54rem
      background: #eeeeee
      padding-left: .2rem
      font-size: .26rem
      color: #666
    .buttom-list
      padding: 0.1rem
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .bottom-wrapper
        width: 33.33%
        float: left
        .bottom
          text-align: center
          margin: .1rem
          padding: .1rem 0
          border: .02rem solid #cccccc
          border-radius: 0.06rem
    .item-list
      .item
        line-height: .76rem
        padding-left 0.2rem
</style>
