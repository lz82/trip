<template>
  <div class="toplink-wrapper">
    <div class="left item">
      <i class="iconfont icon-location"></i><span>定位失败</span>
    </div>
    <div class="right item">
      <i class="iconfont icon-earth"></i><span>必游榜单</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LeftRight',

  data () {
    return {}
  }
}
</script>

<style lang="less" scoped>
.toplink-wrapper {
  background-color: #fff;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  position: relative;
  &:before {
    position: absolute;
    top: 0;
    left: 0;
    content: ' ';
    height: 1px;
    width: 100%;
    transform: scaleY(0.5);
    background-color: #e0e0e0;
  }
  .item {
    flex: 0 0 50%;
    line-height: 49px;
    font-size: 14px;
    display: flex;
    justify-content: center;
    align-items: center;
    .iconfont {
      margin-right: 5px;
    }
  }
  .left {
    display: flex;
    position: relative;
    &:after {
      content: ' ';
      position: absolute;
      right: 0;
      top: 0;
      width: 1px;
      height: 100%;
      background-color: #e0e0e0;
      transform: scaleX(0.5)
    }
  }
  .right {
    display: flex;
  }
}
</style>
