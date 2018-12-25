<template>
  <header class="header-wrapper">
    <a href="" class="left">
      <i class="iconfont icon-left"></i>
    </a>
    <div class="content" @click="onSearchClick">
      <i class="iconfont icon-search"></i>
      <span>输入城市/景点/游玩主题</span>
    </div>
    <div class="position" >
      <router-link to="/city"><span>上海</span><i class="iconfont icon-caret-down"></i></router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',

  data () {
    return {}
  },

  mounted () {},

  methods: {
    onSearchClick () {
      this.$router.push('/search')
    }
  }
}
</script>

<style lang="less" scoped>
.header-wrapper {
  display: flex;
  height: 44px;
  line-height: 44px;
  box-sizing: border-box;
  background-color: #00bcd4;
  color: #fff;
  .left {
    flex: 0 0 40px;
    color: #fff;
    i {
      font-size: 18px;
    }
  }
  .content {
    flex: 1 1 auto;
    background-color: #fff;
    margin: 7px 0;
    border-radius: 4px;
    color: #ccc;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    padding-left: 5px;
    span {
      padding-left: 5px;
      font-size: 14px;
    }
  }
  .position {
    flex: 0 0 66px;
    font-size: 14px;
    a {
      color: #fff;
    }
    i {
      font-size: 12px;
    }
  }
}
</style>
