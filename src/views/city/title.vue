<template>
  <div class="title-wrapper">
    <div class="title">
      <router-link class="arrow" to="/"><i class="iconfont icon-left"></i></router-link>
      <div class="word">城市选择</div>
      <div class="noop"></div>
    </div>
    <div class="switch">
      <ul class="container">
        <li :class="{active: type === 'in'}" @click="changeType('in')">境内</li>
        <li :class="{active: type === 'out'}" @click="changeType('out')">境外·港澳台</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityTitle',

  data () {
    return {
      type: 'in'
    }
  },

  methods: {
    changeType (type) {
      this.type = type
    }
  }
}
</script>

<style lang="less" scoped>
.title-wrapper {
  display: flex;
  flex-flow: column nowrap;
  height: 74px;
  background-color: #00bcd4;
  color: #fff;
  font-size: 16px;
  .title {
    box-sizing: border-box;
    line-height: 34px;
    display: flex;
    flex-flow: row nowrap;
    box-sizing: border-box;
    .arrow {
      flex: 0 0 40px;
      justify-content: center;
      color: #fff;
    }
    .word {
      flex: 1 1 auto;
    }
    .noop {
      flex: 0 0 40px;
    }
  }
  .switch {
    display: flex;
    height: 40px;
    box-sizing: border-box;
    justify-content: center;
    align-items: center;
    .container {
      display: flex;
      flex-flow: row nowrap;
      justify-content: center;
      li {
        display: inline-block;
        width: 156px;
        line-height: 20px;
        border: solid 1px #fff;
        &:first-child {
          border-right-width: 0;
        }
        &.active {
          background-color: #fff;
          color: #00bcd4;
        }
      }
    }
  }
}
</style>
