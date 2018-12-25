<template>
  <div class="banner-wrapper">
    <div class="item left">

    </div>
    <div class="item right">

    </div>
  </div>
</template>

<script>
export default {
  name: 'Banner'
}
</script>

<style lang="less" scoped>
.banner-wrapper {
  background-color: #fff;
  display: flex;
  flex-flow: row nowrap;
  height: 70px;
  position: relative;
  &:before {
    content: ' ';
    position: absolute;
    top: 0;
    left: 0;
    background: #e0e0e0;
    width: 100%;
    height: 1px;
    transform: scaleY(0.5)
  }
  &:after {
    content: ' ';
    position: absolute;
    bottom: 0;
    left: 0;
    background: #e0e0e0;
    width: 100%;
    height: 1px;
    transform: scaleY(0.5)
  }
  .item {
    flex: 0 0 50%;
  }
  .left {
    background: url('//img1.qunarzz.com/piao/fusion/1811/12/999862443f79a902.png') no-repeat center center;
    background-size: cover;
    position: relative;
    &:after {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 1px;
      height: 100%;
      background-color: #e0e0e0;
      transform: scaleX(0.5);
    }
  }
  .right {
    background: url('//img1.qunarzz.com/piao/fusion/1811/d5/20dc542eb839c702.png') no-repeat center center;
    background-size: cover;
  }
}
</style>
