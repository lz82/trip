<template>
  <div class="city-wrapper">
    <title-com  class="nav-wrapper"/>
    <div class="content-wrapper">
      <div>
        <hot />
        <alphabet @move="move"  ref="alphabet"/>
      </div>
    </div>
  </div>
</template>

<script>
import BSCroll from 'better-scroll'
import TitleCom from './title'
import Hot from './hot'
import Alphabet from './alphabet'

export default {
  name: 'City',

  components: {
    TitleCom,
    Hot,
    Alphabet
  },

  data () {
    return {
      scroll: null
    }
  },

  mounted () {
    this.$nextTick(() => {
      this._initData()
    })
  },

  methods: {
    _initData () {
      this.scroll = new BSCroll('.content-wrapper', {
        click: true
      })
    },

    move (key) {
      const element = this.$refs.alphabet.$refs[`city_${key}`][0]
      this.scroll.scrollToElement(element)
    }
  }
}
</script>

<style lang="less" scoped>
.city-wrapper {
  position: relative;
  min-height: 100vh;
  .nav-wrapper {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
  }
  .content-wrapper {
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      top: 75px;
      overflow: hidden;
  }
}
</style>
